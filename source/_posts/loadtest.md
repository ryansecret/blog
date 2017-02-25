---
title: loadtest
date: 2017-01-17 09:41:01
tags:
---
### loadtest 压力测试
可用powershell 或linux bash 

命令行如果加post body 会报错

常用参数：

-T 表示持续时间

-c 并行数量

-n 总的请求

-m  get,put,post

--rps 每秒发送请求数

-P Request body 数据

-p body 数据存在的文件路径

-H header 添加

-C 设置cookie
```
param(
    [int] $iterations = 6000,
    [int] $rps = 500,
    [string][ValidateSet("plaintext")] $variation = "plaintext")

if ($variation -eq "plaintext")
{
    $url = "http://wh.etao.cn/auth/test"
}

Write-Host -ForegroundColor Green Beginning workload
Write-Host "`& loadtest -k -n $iterations -c 100 --rps $rps $url"
Write-Host

& loadtest -k -n $iterations -c 100 --rps $rps $url
```

```
loadtest -c 5 -t 2 -m post -T 'application/json'  -P '{"message":"hello"}'  -H "Accept: application/json; q=0.9, application/xml; q=0.6" http://cttest.etao.cn:8011/api/auth/test
```
