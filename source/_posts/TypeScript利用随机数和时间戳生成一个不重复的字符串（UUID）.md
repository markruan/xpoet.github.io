---
title: 巧妙利用随机数和时间戳生成一个不重复的字符串（UUID）
date: 2018-11-21 17:44:02
tags: [UUID]
categories: [前端]
---

> 此方法非常简单，非常高效...

```typescript
/**
 * 巧妙利用随机数和时间戳生成一个不重复的字符串（UUID）
 * @param randomLength{number} 截取随机数的长度
 * @return {string} 不重复的字符串
 */
export const getUuid = (randomLength: number = 5): string => {
  return Number(Math.random().toString().substr(2, randomLength) + Date.now()).toString(36);
};

// getUuid(5) -> 2l5w9z6sqvg0
```

