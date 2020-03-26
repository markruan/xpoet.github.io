---
title: Angular Material Dialog 拖拽功能的实现
date: 2019-06-28 16:38:51
tags: [Angular, Material]
categories: [Angular]
---

#### Angular版本
本案例使用的Angular版本，但不限于此版本。
- "@angular/core": "^7.0.3"
- "@angular/material": "^7.0.2"

#### 新建Angular指令
新建指令命令：
`ng generate directive dialog-draggable`

指令中拖拽功能代码实现：
```typescript
import { Directive, HostListener, OnInit } from '@angular/core';
import { MatDialogContainer, MatDialogRef } from '@angular/material';
import { Subscription, fromEvent } from 'rxjs';
import { takeUntil } from 'rxjs/operators';

export interface Position {
  x: number;
  y: number;
}

@Directive({
  selector: '[dialog-draggable]'
})
export class DialogDraggableDirective implements OnInit {

  private _subscription: Subscription;

  mouseStart: Position;

  mouseDelta: Position;

  offset: Position;

  constructor(
    private matDialogRef: MatDialogRef<any>,
    private container: MatDialogContainer
  ) {
  }

  ngOnInit() {
    this.offset = this._getOffset();
    this._updatePosition(this.offset.y, this.offset.x);
  }

  @HostListener('mousedown', ['$event'])
  onMouseDown(event: MouseEvent) {
    this.mouseStart = { x: event.pageX, y: event.pageY };

    const mouseup$ = fromEvent(document, 'mouseup');
    this._subscription = mouseup$.subscribe(() => this.onMouseup());

    const mousemove$ = fromEvent(document, 'mousemove')
      .pipe(takeUntil(mouseup$))
      .subscribe((e: MouseEvent) => this.onMouseMove(e));

    this._subscription.add(mousemove$);
  }

  onMouseMove(event: MouseEvent) {
    this.mouseDelta = { x: (event.pageX - this.mouseStart.x), y: (event.pageY - this.mouseStart.y) };

    this._updatePosition(this.offset.y + this.mouseDelta.y, this.offset.x + this.mouseDelta.x);
  }

  onMouseup() {
    if (this._subscription) {
      this._subscription.unsubscribe();
      this._subscription = undefined;
    }
    if (this.mouseDelta) {
      this.offset.x += this.mouseDelta.x;
      this.offset.y += this.mouseDelta.y;
    }
  }

  private _updatePosition(top: number, left: number) {
    this.matDialogRef.updatePosition({
      top: top + 'px',
      left: left + 'px'
    });
  }

  private _getOffset(): Position {
    const box = this.container['_elementRef'].nativeElement.getBoundingClientRect();
    return {
      x: box.left + pageXOffset,
      y: box.top + pageYOffset
    };
  }
}

```

在全局的CSS样式文件添加下面的CSS代码：
```css
[dialog-draggable] {
  margin: -24px -24px 20px -24px !important;
  padding: 10px 24px;
  background: #283593 !important;
  color: #fff;
  cursor: move;
}
```

#### 使用指令
在Dialog组件中使用dialog-draggable指令即可实现窗口拖拽，如下
```html
<h2 mat-dialog-title dialog-draggable>
  Angular Material Dialog Draggable
</h2>
```

#### 拖拽效果视频

#### 线上代码