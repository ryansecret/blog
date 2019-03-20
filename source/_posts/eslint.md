---
title: eslint
date: 2016-12-25 13:31:39
tags:
---

ESLint 一旦发现配置文件中有 "root": true，它就会停止在父级目录中寻找。



```
行内配置


/*eslint-disable*/ 和 /*eslint-enable*/

/*global*/
/*eslint*/
/*eslint-env*/


命令行选项：

--global
--rule
--env

-c、--config



项目级配置：

与要检测的文件在同一目录下的 .eslintrc.* 或 package.json 文件
继续在父级目录寻找 .eslintrc 或 package.json文件，直到根目录（包括根目录）或直到发现一个有"root": true的配置。
如果不是（1）到（3）中的任何一种情况，退回到 ~/.eslintrc 中自定义的默认配置。

```

glob 模式的配置
```json  
{
  "rules": {
    "quotes": [ 2, "double" ]
  },

  "overrides": [
    {
      "files": [ "bin/*.js", "lib/*.js" ],
      "excludedFiles": "*.test.js",
      "rules": {
        "quotes": [ 2, "single" ]
      }
    }
  ]
}

```

ignore 文件配置：

# Ignore built files except build/index.js
build/*
!build/index.js

全局变量
```javascript
  globals: {
        MyGlobal: true
    }
```


 