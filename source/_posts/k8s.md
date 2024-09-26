---
title: k8s
date: 2021-11-18 17:10:24
tags: k8s
---

### helm 
1. 获取values helm get values mongodb-back -n tpaas-mongodb
   
2. helm pull itg/rds-console —version=XXXX —untar

3. helm uninstall $rds_console_chart_name -n ${{out._predefine.NAMESPACE}}

4. helm add repo

`helm repo add itg ${{helm_repo}} --username ${{cred.helm_zhangchong.username}}   --password ${{cred.helm_zhangchong.password}}  `

`helm repo update`

1. 由 helm install -f 或 helm upgrade -f 提供的 value 文件

```
# 安装本地 chart
helm install -f myvalues.yaml myredis ./redis
# 指定变量
helm install --set name=prod myredis ./redis
```

### k8s

1. Service的IP地址，此为虚拟IP地址。外部网络无法ping通，只有kubernetes集群内部访问使用。

1. 由于 Kubernetes 集群中每个 Pod（容器组）都有一个唯一的 IP 地址（即使是同一个 Node 上的不同 Pod），我们需要一种机制，为前端系统屏蔽后端系统的 Pod（容器组）在销毁、创建过程中所带来的 IP 地址的变化。


1. 可以通过 set-context 命令改变当前 kubectl 上下文 的名称空间，后续所有命令都默认在此名称空间下执行。

1. port表示Service对外提供的端口，可以通过“ClusterIP:端口”访问服务。●targetPort表示对应的后端应用（即Pod）的端口。

1.  Sh  -c string：命令从-c后的字符串读取。

1. helm list是区分命名空间的。默认情况下，Helm将Kubernetes配置文件设置的命名空间作为默认命名空间（通常名为default）。

1.   helm get notes mysite  用来打印发布说明

1. helm -n namespace  get values <release-name>    namespace 很关键不然是默认的ns

1. heml install 

```
使用--generate name标志，我们不再需要提供名称作为helm install的第一个参数。Helm根据chart名称和时间戳的组合生成名称。在前面的输出中，我们可以看到生成的名称：wordpress-1597689085。

通过添加--create-namespace，我们已经向Helm表明，我们知道可能还没有具有该名称的命名空间，只希望创建一个。当然，请确保如果在生产实例上使用此标志，会有其他机制来强制执行此新命名空间的安全性。

```

1. apiVersion告诉Helm此chart使用的是什么结构。apiVerison v2是为Helm v3设计的。

1. appVersion属性是唯一的。它既是描述性的，也是模板中经常使用的。appVersion属性表示主应用程序或组合应用程序的版本。例如，如果被打包的应用程序是WordPress，那么它就是WordPress的版本。

1. 重启Pod  

kubectl get pod {podname} -n {namespace} -o yaml | kubectl replace -f -
