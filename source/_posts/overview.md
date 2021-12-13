---
title: overview
date: 2021-12-13 17:38:48
tags:
---

1.  临时安全令牌（Security Token Service，STS）
2.  *** 获取文本px宽度* @param font{String}: 字体样式**

```
String.prototype.pxWidth = function(font) {
  // re-use canvas object for better performance
  var canvas = String.prototype.pxWidth.canvas || (String.prototype.pxWidth.canvas = document.createElement("canvas")),
      context = canvas.getContext("2d"); 3

  font && (context.font = font);
  var metrics = context.measureText(this);

  return metrics.width;
}
```

1. 先保存各个实例的values信息， helm get values [release] > xxx.yaml