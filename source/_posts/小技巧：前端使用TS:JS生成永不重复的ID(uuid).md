---
title: 小技巧：前端使用TS/JS生成永不重复的ID(uuid)
date: 2018-11-21 17:44:02
tags: [前端自动化]
categories: [前端开发]
---

> 此方法非常简单，非常高效...

__废话不多说，直接上代码，本例使用TypeScript：__

```typescript
/**
 * 巧妙利用随机数和时间戳随机生成一个不重复的ID（uuid）
 * @param randomLength{number} 截取随机数的长度
 * @return {string} 不重复的字符串ID
 */
export const getUuid = (randomLength: number = 5): string => {
  return Number(Math.random().toString().substr(2, randomLength) + Date.now()).toString(36);
};
```

