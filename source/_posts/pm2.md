---
title: pm2
date: 2016-12-29 17:53:39
tags:
---
### pm2 start 启动文件的设置

1. 通过 pm2 ecosystem 生成文件
2. 在配置文件中配置，主要参数如下：
　　
```
min_uptime：最小运行时间，这里设置的是60s即如果应用程序在60s内退出，pm2会认为程序异常退出，此时触发重启max_restarts设置数量

exec_mode：应用程序启动模式，这里设置的是cluster_mode（集群），默认是fork
error_file：自定义应用程序的错误日志文件
out_file：自定义应用程序日志文件
pid_file：自定义应用程序的pid文件
watch：是否启用监控模式，默认是false。如果设置成true，当应用程序变动时，pm2会自动重载。这里也可以设置你要监控的文件

exec_interpreter：应用程序的脚本类型，这里使用的shell，默认是nodejs
defaults to “node”. can be “python”, “ruby”, “bash” or whatever interpreter you wish to use. “none” will execute your app as a binary executable

当使用babel的时候： exec_interpreter:"babel-node"
 
max_memory_restart  超出这个内存后会重新启动

```

3. 可以设置watch 的目录
   
```
{
  "name"        : "fis-receiver",  // 应用名称
  "script"      : "./bin/www",  // 实际启动脚本
  "cwd"         : "./",  // 当前工作路径
  "watch": [  // 监控变化的目录，一旦变化，自动重启
    "bin",
    "routers"
  ],
  "ignore_watch" : [  // 从监控目录中排除
    "node_modules", 
    "logs",
    "public"
  ],
  "watch_options": {
    "followSymlinks": false
  },
  "error_file" : "./logs/app-err.log",  // 错误日志路径
  "out_file"   : "./logs/app-out.log",  // 普通日志路径
  "env": {
      "NODE_ENV": "production"  // 环境参数，当前指定为生产环境
  }
}
```

