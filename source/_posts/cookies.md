---
title: cookies
date: 2019-06-24 14:40:18
tags: 零碎
---

:smile:
### 发版
1. 发布阶段：更新chagelog ,打 git tag 。

### word
1. analogy 类比 [əˈnælədʒi]
1. pache [ə’pætʃɪ]
2. deflate 放气，紧缩
3. Sanitize 消毒，净化
4. access [‘ækses]
5. Azure [‘æʒə]
6. avatar [‘ævətɑː]
7. ASCII [‘æski]
8. archive [‘ɑːkaɪv]
9. debt  [det]
10. typical [‘tɪpɪkl]  
11. resume [rɪ'zju:m]
12. parameter [pə’ræmɪtə] 
13. integer  [‘ɪntɪdʒə]
14. matrix [ˈmeɪtrɪks]
15. height [haɪt]
16. shallow  肤浅的 
17. tenant  租户，房客
18. coerce [kəʊˈɜːs]  强制 
19. indeterminate  [ˌɪndɪˈtɜːrmɪnət]
20. sup 一口；饮酒  
21. crumb 面包屑   
22. prune  修剪；减少；
23. Unify 整合、统一 
24. contiguous  kənˈtɪɡjuəs
 

25. 无论你使用的是解释型语言(JavaScript、Python、Ruby)还是编译型语言(c#、Java、Rust)，都有一个共同的部分:将源代码作为纯文本解析为 抽象语法树(abstract syntax tree, AST) 的数据结构。
26. AST 不仅以结构化的方式显示源代码，而且在语义分析中扮演着重要角色。在语义分析中，编译器验证程序和语言元素的语法使用是否正确。之后，使用 AST 来生成实际的字节码或者机器码。

28. 要应用更新，Virtual DOM核心功能将发挥作用，即 协调算法，它的工作是提供最优的解决方案来解决以前和当前虚拟DOM 状态之间的差异。

## opentracing
1. Opentracing 的carrier 有多种实现，tracer 的inject（客户端进程） 和 extract（服务端进程），这样 客户端和服务端 就可以拥有相同的trace context。
1. Server 首先extract check 有没有注入的span，没有的话启动一个新的span

## mac
1. Mac 设置path  export PATH=$PATH:
1.  查看端口占用：lsof -i:3001
1. export http_proxy="http://localhost:8899"
1. Grep -A 5 显示后面5行信息
1. Mac 配置：
   Oh my zsh 
   brew install autojump  
   git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   plugins=(
     git zsh-autosuggestions autojump zsh-syntax-highlighting
   )
   
   
## npm
1. npm config edit
1. npm config set init.author.name "ryansecreat"
1. npm config set init.email='chenjingnan@jd.com’
1. npm config set init.license "MIT"
1. npm start --prefix path/to/your/folder   //指定目录下运行
1. npm repo   浏览器中打开repo
1. npm publish --registry=http://registry.npmjs.org  --registry=https://registry.npm.taobao.org
1. npm outdated  查看过时package
1. npm publish --tag=beta.
1. npm version patch -m "Upgrade to %s for reasons”
1. npm dist-tag add n-n-n-n@1.0.2-1 latest  将某个预发版本更新为最新   
1. npm ping [--registry <registry>]

 

  
### vim 
j: 下移一行；

k: 上移一行；

w: 前移一个单词，光标停在下一个单词开头；

e: 前移一个单词，光标停在下一个单词末尾；

0: 移动到行首。

$: 移动到行尾。

n|: 把光标移到递n列上

zz: 将当前行移动到屏幕中央。

o: 在下面新建一行插入；

O: 在上面新建一行插入；

a: 在光标后插入；

A: 在当前行最后插入；

u: 取消一(n)个改动。

ctrl + r: 重做最后的改动。