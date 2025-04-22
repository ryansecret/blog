---
title: overview
date: 2021-12-13 17:38:48
tags: overview
---
1. Webpack Loader 和 Plugin 的区别
定义
Loader：用于对模块进行转换，如将 TypeScript 转换为 JavaScript，或将 SASS/CSS 转换为 JavaScript。
Plugin：用于在 Webpack 构建流程中执行更复杂、更广泛的任务，如代码压缩、资源管理、HTML 文件生成等。

1. lazy 渲染
```
display: block; // 必须为块级元素
content-visibility: auto;
contain-intrinsic-size: auto 100px;
```
2. timeago.js
```
timeage.format(1544666010224, 'zh_CN') // 输出 “5 年前” 
timeage.format(Date.now() - 1000, 'zh_CN') // 输出 “刚刚” 
timeage.format(Date.now() - 1000 * 60 * 5, 'zh_CN') // 输出 “5 分钟前”
```

1. Temporal提案引入了一个新的API，以更直观和高效的方式 处理日期和时间。例如，Temporal API提供了新的日期、时间和持续时间的数据类型，以及用于创建、操作和格式化这些值的函数。
2. Cavas 绘图 leafJs 和 vue leaf
3. 一些 CDN 资源不受同源策略限制，是因为同源策略主要是浏览器的一种安全机制，用于限制不同源的文档或脚本之间的交互操作，
这样做的主要原因是为了保证 Web 的开放性和可扩展性。如果这些资源也严格受到同源策略的限制，那么将所有相关资源都部署在同一个服务器下会违背 Web 开放的初衷，并且不利于资源的分发和缓存
1. babel-runtime 的主要作用就是将这些可能被重用的代码抽取成单独的模块，以避免在每个文件中重复出现相同的代码。它通过模块导入的方式引入这些功能，从而避免了对全局作用域的修改或污染。
具体来说，babel-runtime 包含了诸如 core-js（提供 JavaScript 内置库的垫片，如 array、json、math、promise、symbol 等）、regenerator-runtime（实现了 generator/yield、async/await）以及一些语法转换的辅助函数（如 es5 与 es6 的继承转换等）。
1.  axios-auth-refresh 同样是刷新验证
2.  axios-jwt  Store, clear, transmit and automatically refresh JWT authentication tokens
3.  barba.js
    Create badass, fluid and smooth transitions between your website’s pages
4. 通过应用text-wrap: balance属性，浏览器将自动计算单词数并将它们平均分配到两行——非常适合页面标题、卡片标题、工具提示、模态框和FAQ等。

5. 可以使用 :focus-visible 使其仅在键盘操作时才显示焦点样式。这和<button>一类的原生控件表现一致。
6.  
```
:has() 是一种伪类选择器，也被称为 “关系选择器”，它允许你根据元素是否包含特定的其他元素（满足括号内指定的条件）来选择该元素本身。
.box:has(.selected){
      background-color: red;
}
// 当前hover 元素的上一个元素
.layout-container .item:has(+ *:hover) {
  filter: brightness(0.6);
  transform: translateZ(150px) rotateY(-40deg);
}
```
1. body { color-scheme: light dark; /* 启用浅色模式和深色模式 */ color: light-dark(#333, #fff); /* 文本浅色和深色颜色 */ background-color: light-dark(#fff, #222); /* 背景浅色和深色颜色 */ }
2. refline.js是完全不依赖设计器环境的参考线组件，方便各种设计器快速接入，支持参考线匹配及吸附功能。
3. https://github.com/fabiospampinato/cash  js 操作库，like jquery，相对更小
4. Offfice 文件预览 kkfile  vue-office
5. 原生的HTML属性完全可以实现hidden。效果类似于添加样式display: none;
6. 浏览器会根据用户的系统设置自动选择使用哪种颜色。
7. simple-mind-map   js 思维导图
8. animation-timeline用于指定动画的时间线。
9. view()，它可以使动画的时间线基于视口的滚动或其他动态因素进行控制。
10. vue-virtual-scroller 虚拟化列表
11. brightness   CSS <filter-function> applies a linear multiplier value on an element or an input image, making the image appear brighter or darker.
12. Chevrotain   js 语言解释工具
13. event source 连接建立	基于 HTTP 协议，客户端发起特殊请求，服务器响应；数据传输格式：事件流格式，每个事件由事件类型和数据组成
14. https://d2lang.com/tour/icons 相对于meimaid 更专业的更复杂的图 
15. https://file.ch3nyang.top/   用来传文件
16. CSS margin-trim属性设置在容器元素上，可以让子元素（需边缘接触）的margin设置计算值变成0。
Dexie.js is a wrapper library for indexedDB

1. 大屏编辑器  https://github.com/MrXujiang/v6.dooring.public
2. natapp 内网穿透
3. ngrok 内网穿透  https://juejin.cn/post/6844903815867531278?searchId=20241230094646F4A8A6C4188D3B842710
4. Mac networkQuality  测试网速 
5. caffeinate will keep your Mac awake until you stop it, e.g. by pressing Ctrl+C.
6. https://www.shadcn-vue.com/   

Beautifully designed components that you can copy and paste into your apps. Accessible. Customizable. Open Source.
2. shape-outside 用来处理图形和文字的布局
3.  backdrop-filter: blur(10px);   用于模糊背景
4.  Raycast alfred 替代体
5.  Hoppscotch is a lightweight, web-based API development suite.
6.  Infisical is the open source secret management platform that developers use to centralize their application configuration and secrets like API keys and database credentials as well as manage their internal PKI. Additionally, developers use Infisical to prevent secrets leaks to git and securely share secrets amongst engineers. 用来存储程序的敏感信息。
7.  FinalShell  ssh工具
8.  TOTP 的全称是"基于时间的一次性密码"（Time-based One-time Password）
9.  HSL 是一种颜色表示方式，它代表色相（Hue）、饱和度（Saturation）和亮度（Lightness）。在 CSS 中，HSL 颜色模式是一种用于指定颜色的方法，它使用三个值来描述颜色：色相、饱和度和亮度。hsl(hue, saturation, lightness)
其中，hue 表示色相，saturation 表示饱和度，lightness 表示亮度。每个值都可以是一个百分比或者一个介于 0 到 360 之间的整数。
1. SharedWorker API 是 HTML5 中提供的一种多线程解决方案，它可以在多个浏览器 TAB 页面之间共享一个后台线程，从而实现跨页面通信。
与其他 Worker 不同的是，SharedWorker 可以被多个浏览器 TAB 页面共享，且可以在同一域名下的不同页面之间建立连接。这意味着，多个页面可以通过 SharedWorker 实例之间的消息传递，实现跨 TAB 页面的通信。
1.  File 是 JavaScript 中代表文件的数据结构，它继承自 Blob 对象，包含文件的元数据（如文件名、文件大小、类型等）。File 对象通常由用户通过 <input type="file"> 选择文件时创建，也可以使用 JavaScript 构造函数手动创建。
2.  localStorage:仅在客户端存储不参与服务器通信，存储大小一般为5M
3.  如果用 Blob 发送数据，这时需要我们手动设置 Blob 的 MIME type， // 一般设置为 application/x-www-form-urlencoded。 const reportData = (url, data) => { const blob = new Blob([JSON.stringify(data), { type: ' type: 'application/json'', }]); navigator.sendBeacon(url, blob); };
``发送数据大小限制 目前没有给出具体的发送数据大小限制标准，不过有人做了下面的测试，当数据长度是65536时，异步请求进入浏览器发送队列失败，表明数据大小是有限制，不同的浏览器应该有所差别。``
4.  1em 表示的是当前元素的字号，可以看到 1em 是 16px，因为当前元素的 font-size 是 16px，浏览器会根据相对单位 em 计算出绝对单位 px，所以当你改变了这个元素的 font-size，其对应的 padding 也会随之变化，设置 padding、height、width、border-radius 这些属性的时候，使用 em 很方便，会动态根据 font-size 变化
5.  通过百分比设置   html { font-size: 62.5%; }
6.  「rem」是指根元素（root element，html）的字体大小，好开心的是，从遥远的 IE6 到版本帝 Chrome 他们都约好了，根元素默认的 font-size 都是 16px。 
7.  汉字转拼音  https://github.com/overtrue/pinyin
8.  npm disturl 是一个配置项，用于设置npm下载tarball包（通常是Node.js的二进制文件或者一些带有平台相关编译内容的npm模块）时的基础URL。当npm需要从源代码构建依赖项，并且这些依赖项包含需要从特定位置下载的预编译二进制文件时，它会使用这个disturl来定位和下载这些文件。
9.  Python 问题 ： brew install python-setuptools
10. width: fit-content   父级大小适配

11. 为了防止 DNS Rebinding 攻击，webpack-dev-server 会取请求头的 host/orign 和配置的 devServer.host 或 devServer.public 做比较，只允许配置相同的请求   
12. WSS（Web Socket Secure）是WebSocket的加密版本。WS一般默认是80端口，而WSS默认是443端口，大多数网站用的就是80和433端口。
wss://test.foo.com ws://localhost:4900
将加密的转发到本机不加密的
1. HTTP Strict Transport Security   HSTS   grid-auto-flow  
2. * justify-content:space-evenly:项目与项目的间隔相等，项目与容器边框之间也是同样长度的间隔
3. 你知道CSS的inset属性吗？这是我们所熟悉的top，left，right和bottom的缩写版本。通过类比短语法margin或属性padding，只要一行代码就可以设置元素的所有偏移量。

4. 生成用户指纹
   https://github.com/fingerprintjs/fingerprintjs
   浏览器指纹是无状态的，它无需用户授权便可收集信息，并且不会像 Cookie 一样会被用户禁止或清除，只要你的指纹是唯一的，你就能够被唯一识别和跟踪。当然，一个事物的好坏是取决于怎么使用它，浏览器指纹也可用于一些好的方面，比如：反欺诈，防止刷票、黄牛、机器人，异地或者可疑登录提示，多设备管理，或者在注重用户隐私的情况下，进行一些数据分析，提高用户体验。
 
5. CSS 选择器允许多次出现相同的简单选择器，而且可以增加权重。
/* 双重 .checkbox__icon！权重现在是 (0,4,0) */
.newsletter .newsletter__checkbox .checkbox__icon.checkbox__icon {
  top: 5px;
}
1. xterm-pty
   This is an addon that adds a PTY layer to xterm.js. It is useful to run an Emscripten'ed CUI program.
2. 
在开发过程中，我们经常需要与命令行进行交互。而如今，node-pty提供了一种全新的方式来实现这一功能，它是一个强大的跨平台终端仿真库，让你能够在Node.js环境中轻松地创建和控制子进程，仿佛它们是真正的终端。   
1. tidb
```
Tidb

* 一键水平扩缩容得益于 TiDB 存储计算分离的架构的设计，可按需对计算、存储分别进行在线扩容或者缩容，扩容或者缩容过程中对应用运维人员透明。
* 金融级高可用数据采用多副本存储，数据副本通过 Multi-Raft 协议同步事务日志，多数派写入成功事务才能提交，确保数据强一致性且少数副本发生故障时不影响数据的可用性。可按需配置副本地理位置、副本数量等策略，满足不同容灾级别的要求。
* 实时 HTAP提供行存储引擎 TiKV、列存储引擎 TiFlash 两款存储引擎，TiFlash 通过 Multi-Raft Learner 协议实时从 TiKV 复制数据，确保行存储引擎 TiKV 和列存储引擎 TiFlash 之间的数据强一致。TiKV、TiFlash 可按需部署在不同的机器，解决 HTAP 资源隔离的问题。
* 云原生的分布式数据库专为云而设计的分布式数据库，通过 TiDB Operator 可在公有云、私有云、混合云中实现部署工具化、自动化。
* 兼容 MySQL 协议和 MySQL 生态兼容 MySQL 协议、MySQL 常用的功能、MySQL 生态，应用无需或者修改少量代码即可从 MySQL 迁移到 TiDB。提供丰富的数据迁移工具帮助应用便捷完成数据迁移。


* TiDB Server：SQL 层，对外暴露 MySQL 协议的连接 endpoint，负责接受客户端的连接，执行 SQL 解析和优化，最终生成分布式执行计划。TiDB 层本身是无状态的，实践中可以启动多个 TiDB 实例，通过负载均衡组件（如 LVS、HAProxy 或 F5）对外提供统一的接入地址，客户端的连接可以均匀地分摊在多个 TiDB 实例上以达到负载均衡的效果。TiDB Server 本身并不存储数据，只是解析 SQL，将实际的数据读取请求转发给底层的存储节点 TiKV（或 TiFlash）。

* PD (Placement Driver) Server：整个 TiDB 集群的元信息管理模块，负责存储每个 TiKV 节点实时的数据分布情况和集群的整体拓扑结构，提供 TiDB Dashboard 管控界面，并为分布式事务分配事务 ID。PD 不仅存储元信息，同时还会根据 TiKV 节点实时上报的数据分布状态，下发数据调度命令给具体的 TiKV 节点，可以说是整个集群的"大脑"。此外，PD 本身也是由至少 3 个节点构成，拥有高可用的能力。建议部署奇数个 PD 节点。

* 存储节点

    * TiKV Server：负责存储数据，从外部看 TiKV 是一个分布式的提供事务的 Key-Value 存储引擎。存储数据的基本单位是 Region，每个 Region 负责存储一个 Key Range（从 StartKey 到 EndKey 的左闭右开区间）的数据，每个 TiKV 节点会负责多个 Region。TiKV 的 API 在 KV 键值对层面提供对分布式事务的原生支持，默认提供了 SI (Snapshot Isolation) 的隔离级别，这也是 TiDB 在 SQL 层面支持分布式事务的核心。TiDB 的 SQL 层做完 SQL 解析后，会将 SQL 的执行计划转换为对 TiKV API 的实际调用。所以，数据都存储在 TiKV 中。另外，TiKV 中的数据都会自动维护多副本（默认为三副本），天然支持高可用和自动故障转移。

    * TiFlash：TiFlash 是一类特殊的存储节点。和普通 TiKV 节点不一样的是，在 TiFlash 内部，数据是以列式的形式进行存储，主要的功能是为分析型的场景加速。


```   
2. clickhouse
```
云数据库ClickHouse是开源列式数据库ClickHouse的云上托管服务，数据库内核完全兼容开源社区版本。阿里云提供了一套企业级数据库管理平台，增强了数据安全、集群动态扩容、监控运维等企业级功能，与云上其他数据产品打通，可以便捷地构建云上海量数据分析平台。

云数据库ClickHouse是面向联机分析处理的列式数据库，支持SQL查询，且查询性能好，特别是基于大宽表的聚合分析查询性能非常优异，比其他分析型数据库速度快一个数量级。主要特性如下。

交互式报表
* 		基于ClickHouse和BI工具构建实时运营监控报表
  利用ClickHouse构建实时交互式报表，实时分析订单、收入、用户数等核心业务指标；构建用户来源分析系统，跟踪各渠道PV、UV来源。

* 海量数据实时多维查询
    * 		在数亿至数百亿记录规模大宽表，数百以上维度自由查询，响应时间通常在100毫秒以内。让业务人员能持续探索式查询分析，无需中断分析思路，便于深挖业务价值，具有非常好的查询体验。  

用户画像分析
随着数据时代的发展，各行各业数据平台的体量越来越大，用户个性化运营的诉求也越来越突出，用户标签系统，做为个性化千人千面运营的基础服务，应运而生。如今，几乎所有行业（如互联网、游戏、教育等）都有实时精准营销的需求。通过系统生成用户画像，在营销时通过条件组合筛选用户，快速提取目标群体。

* 基于ClickHouse构建用户特征行为分析系统
    * 		利用ClickHouse对人群标签数据进行实时筛选并进行群体画像统计；自定义条件对海量明细日志记录进行过滤，分析用户行为。
* 用户分群统计
    * 		构建用户特征大宽表，任意选择用户属性标签数据和筛选条件，进行人群特征统计分析。

* 访客来源分析展示
    * 		通过批量离线计算对用户访问日志中的用户行为进行关联，生成用户行为路径大宽表同步到ClickHouse，基于ClickHouse构建交互式访客来源探索分析可视化系统。


携程旅行网是中国领先的综合性旅行服务公司，提供酒店预订、机票预订、旅游度假等服务。携程在数据处理和分析方面面临着海量数据、高并发查询和复杂业务逻辑的挑战。为了应对这些挑战，携程采用了 ClickHouse 作为其数据仓库和数据分析平台。ClickHouse 帮助携程实现了以下目标：
* 快速处理海量数据：携程每天需要处理数百万条订单数据，ClickHouse 可以高效地处理这些数据，使得数据分析和查询更加快速。
* 高并发查询：携程需要应对高并发的查询需求，ClickHouse 可以支持高并发查询，使得数据分析和查询更加高效。
* 灵活的业务逻辑：携程的业务逻辑非常复杂，需要根据不同的维度和指标进行数据分析和查询，ClickHouse 提供了灵活的数据建模和查询语言，可以满足携程的复杂业务需求。
通过使用 ClickHouse，携程可以更加高效地管理数据、进行数据分析和查询，为业务决策提供有力的支持。

* 缺乏广泛的社区支持：虽然 ClickHouse 是一款开源免费的工具，但其社区支持仍然相对较弱。与其他热门开源项目相比，ClickHouse 的社区规模和贡献可能较少。
```
2. mongodb  	•	分片集群可以提供更加良好的水平扩展能力。在分片集群架构中，各个节点以副本集架构为基础，通过数据分片存储的方式实现高并发读写。您可以通过扩展分片集群架构中的Mongos、Shard节点数量和规格实现IO吞吐和存储等能力的扩展。
```
   集群架构
分片服务（shard）和配置服务（configserver）采用三节点副本集架构，稳定可靠；支持代理服务（mongos）和分片服务（mongos）灵活配置个数，线性扩展数据库系统的存储空间及读写性能。

灵活多变的业务场景
云数据库MongoDB采用No-Schema的方式，免去您变更表结构的痛苦，非常适用于初创型的业务需求。您可以将模式固定的结构化数据存储在RDS（Relational Database Service）中，模式灵活的业务存储在MongoDB中，高热数据存储在云数据库Redis或云数据库Memcache中，实现对业务数据高效存取，降低存储数据的投入成本。

物联网应用
云数据库MongoDB具有高性能和异步数据写入功能，特定场景下可达到内存数据库的处理能力。同时，云数据库MongoDB中的分片集群实例，可按需配置Mongos和Shard组件的配置和个数，性能及存储空间可实现无限扩展，非常适合物联网高并发写入的场景。详情请参见变更配置方案概览。

海量数据下，性能优越
* 在使用场合下，千万级别的文档对象，近 10G 的数据，对有索引的 ID 的查询不比MySQL慢，而对非索引字段的查询，则是全面胜出。MySQL实际无法胜任大数据下任意字段的查询，而MongoDB的查询性能令人惊讶。写入性能同样很令人满意，同样写入百万级别的数据，MongoDB比我以前使用过的CouchDB要快得多，基本 10 分钟以下可以解决。观察过程中，MongoDB远算不上 CPU 杀手。

 内置Auto-Sharding自动分片支持云级扩展性，分片简单

劣势：
* 不支持事务操作
* 所有事务要求严格的系统（银行系统）肯定不能用它。
* MongoDB占用空间过大
```
2. 
3. Proxy集群版实例，适用于数据容量较大、QPS要求较高的业务场景。该架构类型实例默认提供Proxy代理，当客户端请求时将由代理节点转发至Redis数据节点，通过代理实现负载均衡、长连接等功能特性，
 ```
     Cluster是一个无中心的分布式架构，高可用切换机制已内置进集群，其QPS性能优于Proxy集群版实例。

代理模式：客户端通过单机的方式进行连接，流量会通过代理转发到Redis节点，有一些命令使用会受限制

直连模式： 数据流量将直接访问Redis节点。 注意：需要使用支持cluster协议的客户端。
 ```   
 

2. 双机热备，自动切换。当主节点发生故障后，从节点会被迅速提升为新的主节点，继续提供服务。
3. 灾备实例通过内网专线同步，具有较低的同步时延和更高的稳定性，同步链路质量远优于公网网络。
         目前推广期专线流量费用免费，商业化收费时间将另行通知。
4. 使用主备高可用架构，避免了数据库的单点风险。
5. 提供独立的数据库连接地址，灾备实例可提供读访问能力，用于就近接入、数据分析等场景，设备冗余成本低。
6. 创建只读实例成功后，您可以开启读写代理，在程序中配置读写代理的地址，由读写代理实现读请求被自动转发到只读实例，写请求被自动转发到主实例。
7. 创建RDS实例后， 会自动将实例所在的VPC段添加至白名单中，即该VPC段中所有的IP都可以访问。
8. 透明数据加密（Transparent Data Encryption (简称TDE)）是指可以在文件层对数据和文件进行实时加密和解密，落盘的文件是加密后的内容，而对于上层应用系统和开发人员而言，加解密过程是无感知的，写入和读取的内容是明文内容，所以叫做透明数据加密
9.  高可用  免费开启读写分离，实现读写请求自动分流，减轻主实例压力。

10. 半同步复制（Semisynchronous replication），介于异步复制和全同步复制之间，主库在执行完客户端提交的事务后不是立刻返回给客户端，而是等待至少一个从库接收到并写到relay log中才返回给客户端
11. 三节点 数据复制方式是强一致性。金融证券对数据一致性要求高的。
12. Zod is a TypeScript-first schema declaration and validation library
13. vsce login ryansecreat
14. vue-object-state A typescript library that helps you keep track of changes in your dtos
15. Vue 脚手架 https://github.com/vuejs/awesome-vue?tab=readme-ov-file#scaffold
16. https://oruga-ui.com/documentation/  headless UI 
17. https://vue-highlight-text.surge.sh/ 高亮显示
18. FZF (stylised as fzf)  is a command line based fuzzy finder built using Golang
```
const list = ['go', 'javascript', 'python', 'rust', 
              'swift', 'kotlin', 'elixir', 'java', 
              'lisp', 'v', 'zig', 'nim', 'rescript', 
              'd', 'haskell']

const fzf = new Fzf(list)
const entries = fzf.find('li')
console.log('ranking is:')
entries.forEach(entry => console.log(entry.item)
```
1. Highlights https://vue-highlight-text.surge.sh/#Example
2. vue network 画图工具 https://dash14.github.io/v-network-graph/getting-started.html 
3. VNT  一个简单、高效、能快速组建虚拟局域网的工具
4. 根据路由生产面包屑  https://nxtchg.github.io/pieces/vue/vs-crumbs/#/foo/bar
5. Vue breads 与vuerouter 相结合 https://scrum.github.io/vue-2-breadcrumbs/
6. 根据vue文件生产文档  https://vuese.github.io/vuese-explorer/
7. numeral 处理number
8. 在线代码编辑： https://stackblitz.com/
9. JSON5 is an extension to the popular JSON file format that aims to be easier to write and maintain by hand

json5 是json 的超集，key  可以不加引号
1. du -sh * | sort -n     查询文件大小
2. 
3. Window.getComputedStyle()方法返回一个对象
4. consola  Elegant Console Wrapper
1. 网络访问控制列表（Access Control List，ACL）是一个子网级别无状态的可选安全层，用于控制进出子网的数据流，可以精确到协议和端口粒度，可用作防火墙来控制进出一个或多个子网的流量。没有网络ACL的保护或者没有配置访问控制策略，会导致子网中的服务器所有网络端口更容易在互联网上遭受攻击甚至导致被入侵。
2. 安全组是一种分布式、有状态的包过滤功能的虚拟防火墙，通过配置安全组规则策略对云主机的出入流量进行安全过滤，实现对云主机的网络访问控制。创建云主机时，须关联相应的安全组，将同一地域内具有相同网络安全隔离需求的云资源加到同一个安全组内，从而控制多个资源的访问流量。
3. 副本集架构
    副本集提供3、5、7节点架构，其中包含一个可供读写访问的Primary节点，一个Hidden节点，实例中剩余节点为只读节点。同时，京东云提供扩缩容能力，帮助您按业务需求进行服务器的部署。

副本集	MongoDB副本集是一组维护相同数据集的Mongod进程，副本集提供冗余和高可用，是所有生产部署的基础。

分片集群	分片是一种用于在多台计算机之间分配数据的方法，MongoDB使用分片集群来支持具有非常大数据集和高吞吐量操作的部署，每个分片集群包含Mongos、Shard、Config Server三种组件。
1.   单可用区部署   可以承受机架级别的故障。
2.   多可用区部署   可以承受机房级别的故障，但因为不同可用区之间存在一定的网络延迟，所以对于单个更新的响应时间多可用区部署会比单可用区部署长
3.   kafka
   ```
   1 提高京东云 Kafka的吞吐量:
​ Kafka中主题topic作为主要接受消息的载体，一般会分成一个或多个分区partition，每个partiton相当于是一个子queue，多个partition就相当于多个子queue在同时工作进行写盘和交互处理，因此增加partition可以增加单个主题topic的吞吐量。在物理结构上，每个partition对应一个物理的文件，Kafka中会把消息持久化到本地文件系统中，并且保持o(1)极高的效率。磁盘的IO读写是非常耗资源的性能，所以提高磁盘的iops和吞吐量，可以提高消息写入磁盘的速度，相应的提高吞吐。Kafka中的主题都是由消费组consumer group来消费的。如果这个consumer group里面consumer的数量小于topic里面partition的数量，就会有consumer thread同时处理多个partition。如果这个consumer group里面consumer的数量大于topic里面partition的数量，多出的consumer thread就会闲置，剩下的是一个consumer thread处理一个partition，这就造成了资源的浪费，因为一个partition不可能被两个consumer thread去处理。

建议：1）增加分区数partition可以有效的提高消息的吞吐量，并且分区数最好是集群处理节点broker的整数倍，这样每个副本分配到的分区数比较均匀。

​ 2）采用高iops和高吞吐的磁盘规格和SSD类型的磁盘。

​ 3）增加生产者producer和消费者consumer的数量，并且消费者的数量最好可以和分区数相等。


我们把多个 consumer实例放在一个group里有什么好处吗？实际上，consumer group是用于高伸缩性，高容错性的consumer机制。组内多个consumer实例可以同时读取kafka消息，而一旦某个consumer挂了，group会立即崩溃，这时候负责的分区交给其他consumer负责，从而保证group可以正常工作。这过程我们称呼为 重平衡（rebalance）。
   ```
4.   redis
   ```
   海量存储，无限容量。集群版采用分布式架构，数据分布在多台物理机上，突破单机物理限制，解决海量数据存储在 Redis 上的瓶颈
   工作时主节点和从节点数据实时同步，当主节点故障时，系统将在15秒左右将从节点提升为主节点，开始提供服务。当完全恢复后，主从所在的AZ会跟创建时保持一致。
   ES集群将部署在 VPC 内，只有在同一个VPC下才能访问ES集群，因此为保证内网顺利访问，建议选择已有云上业务的区域位置所在 VPC。多可用区部署模式下，也是选择同一个 VPC。同一个 VPC 内，不同可用区子网之间是互通的。
   ```
  
5.   tidb
    ```
全新的分布式数据库，支持PB级数据容量，集群QPS上百万。
真正的多活架构，多个节点可以同时提供数据读写服务，并且读写能力均可通过增加节点的方式进行水平扩展。
整个集群数据强一致，所有节点读取的数据均为最新数据，无传统主从架构的数据延迟问题。
与 MySQL 高度兼容，使用 TiDB 像使用单机MySQL一样简单，可以从 MySQL 无缝切换到 TiDB，几乎无需修改代码。
可直接在同一份数据上进行高效的数据查询、分析，简化了架构，提升了数据分析的实时性，同时降低了成本。
全面支持IPV6。
    ```
1. 多活架构及故障自恢复
    真正的多活架构，各个节点均可读写。TiDB 使用多副本进行数据存储，并依赖业界最先进的 Raft 多数派选举算法确保数据 100% 强一致性和高可用。主副本故障时自动切换，无需人工介入，自动保障业务的连续性。
2. 水平弹性扩展

分布式的 TiDB 可随着数据增长而无缝地水平扩展，只需要通过增加更多的机器来满足业务增长需要，应用层可以不用关心存储的容量和吞吐。 TiDB 根据存储、网络、距离等因素，动态进行负载均衡调整，以保证更优的读写性能。    
2. 将表中的数据按照一定的规则拆分为多个部分，每个部分的数据均存储在不同的计算节点上，每个计算节点上的数据称为一个分片。    
3. 可用区是指在同一地域下，电力、网络等基础设施互相独立的物理区域。一个地域包含一个或多个可用区，同一地域下的多个可用区可以彼此连通   
4. 实例是一个独立占用CPU和内存资源的的数据库服务进程，您可在实例中创建或管理多个数据库。
5. 在集群中，需要先部署 Ingress Controller，再创建 Ingress 资源对象。Ingress Controller 控制器是一个 docker 容器，容器镜像中包含一个负载均衡器（比如：Nginx 或是 HAProxy）和一个 Ingress Controller。
6. helm get values  terrabase-console-runtime-76887c7974-qtglz  -n tpaas-terrabase   
7. kubectl edit ing dts-console-ingress -n tpaas-dts 
8. css selector
   ```
   选中后面有h2的h1
   h1:has(+ h2) {
     margin: 0 0 0.25rem 0;
   } 

   is 更精炼的使用selector 
   ul li,
   ol li {}
   等于 
   :is(ul, ol) li {}
   
   body:has(video, audio) {
     /* styles to apply if the content contains audio OR video */
   }
   body:has(video):has(audio) {
     /* styles to apply if the content contains both audio AND video */
   }

   这两个函数的区别在于 :where() 函数的优先级总是零，则 :is() 函数的优先级取决于其最特定参数的优先级。
   ```
9.  docker build -f ./Dockerfile.base . --build-arg TPAAS_RUNTIME_IMAGE=hub.jdcloud.com/baseimages/openeuler:22.03lts-amd64-depends-tools-v20220801
10. find ./ -type f -name yarn.lock
11. Sqids  Sqids (pronounced "squids") is an open-source library that lets you generate YouTube-looking IDs from numbers
12. ssh-keygen -R ip 清理问题ip
13. monaco.editor.setModelMarkers(model, "owner", markers); 标记下划线并给出hint
14. 添加命令  editor.addCommand(monaco.KeyMod.CtrlCmd   可以监控keys 事件  
15. addAction 添加右键菜单和快捷键
16. 显示到对应位置的内容，指定行和列  revealPositionInCenter ·
17. tokenizer 做匹配，rules 指定样式  
18. registerFoldingRangeProvider 提供折叠功能
19. provideHover 提供hover {range,contents}
20. provideInlayHints 提供decorator 的hint
21. 那就是它们有不同的特殊性。:where() 是简单的，其特异性总是为0，而 :is() 的特异性为最强的选择器。
22. 特异性等级评分：
ID——特异性得分为 100
内联样式——特异性得分为 1000
元素和伪类——特异性得分为 1
类、伪类和属性——特异性得分为 10
1.  helm get values mongodb-back -n tpaas-mongodb
2.  marker:text-sky-400 用量设置List marker 的样式
3.  VScode 设置参数
   ```
   {
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
        {
            "label": "kill: process",
            "type": "shell",
            "command": "kill",
            "args": [
                "-9",
                "${input:pid}",
            ],
            "problemMatcher": []
        }
    ],
    "inputs": [
        {
            "id": "pid",
            "type": "pickString",
            "description": "pid to kill",
            "command": "pgrep",
            "args": [
                "${input:procesName}"
            ]
        },
        {
            "id": "procesName",
            "type": "promptString",
            "description": "process name",
            "default": "code"
        }
    ]
}
   ```
1. 需要在不同环境下加载npm包不同的入口文件，显然一个 main 字段已经不能够满足我们的需求，这就衍生出来了 module 与 browser 字段。
https://github.com/SunshowerC/blog/issues/8
1. ts-morph  Setup, navigation, and manipulation of the TypeScript AST 
2.  获取文字长度
   ```
     function getwidth(txt, font) {
      var canvas = document.createElement('canvas')
      var ctx = canvas.getContext('2d')
      ctx.font = font
      return ctx.measureText(txt).width
    }
   ```
3. headless ui  https://headlessui.com/ 
4. @rollup/plugin-node-resolve  自动添加路径index
5. backdrop:bg-gray-50 设置蒙板
6.  first-letter:text-7xl  first-line:uppercase
7. vscode plugin 发布   https://code.visualstudio.com/api/working-with-extensions/publishing-extension     
8. aimless The missing JS randomness library
9. vue-js-modal  
10. gogocode 其中 $_$1 和 $_$2 相当于正则中的通配符，但是在这里只会匹配代码里有效的 AST 节点，$$$ 则可以匹配剩下的节点
11. window.__INJECTED_PUBLIC_PATH_BY_QIANKUN__，是 qiankun 提供的。根据源码分析，它会拿到微应用html入口url之后，将pathname的最后一项去掉，再组装起来。譬如，子应用入口配置：http://local.soame.domain/mar...，那么经过处理后，会变成http://local.soame.domain/

12. const SpeedMeasurePlugin = require('speed-measure-webpack-plugin')  查看webpack 速度
13. 一个专注于前端视觉效果的集合应用，包含CSS动效、Canvas动画、人工智能应用等上百个案例 https://github.com/hepengwei/visualization-collection/tree/master
14. npm i <alias>@npm:<packageName>@<version>   一个包安装不同的版本  
15. Chokidar    Minimal and efficient cross-platform file watching library
16. koa2-connect   Use Express/Connect middleware with Koa.
17. npm list -g --depth 0  
18. 容器内使用 printenv 命令来查看容器内的环境变量。
19. daisy-init --origin direct:https://coding.jd.com/daas-fe/dms-new-console.git --branch template
20. npm cache clean --force    npm cache verify
21. utilities 模块包含的是原子化的样式（每一个基础类都只实现一个基础的样式功能），应该最后加载的。这样在其中定义的样式就有最高的优先级，即确保基础类应用到 HTML 页面时，可以覆盖其他样式。
  所有使用 @layer 添加的样式，它们的类名在应用到 HTML 页面时，也像 Tailwind 内置的基础类一样，都支持使用状态变量（这是使用普通方式添加的样式所不具有的优势）

   而且使用指令 @layer 添加自定义样式，也会在编译时自动进行简化 purge 处理，只有在 HTML 页面的元素中使用了类名，相应的自定义样式才会被编译到最终的样式表中。如果希望自定义的样式最后总是编译到样式表中，则可以不使用指令 @layer 直接写在主样式表中（也需要注意 CSS 代码添加的顺序，一般应该保证 @tailwind utilities 模块最后引入）
1. @tailwindcss/line-clamp
2. list-disc. list-decimal
3. form.resetfileds 需要form-item 设置prop,form设置 model 
4. Selecting all text in one click
     Use select-all to automatically select all the text in an element when a user clicks。
5. text-[12px] 指定字体大小
6. Using spaces and underscores
   Since whitespace denotes the end of a class in HTML, replace any spaces in an arbitrary value with an underscore:<div class="before:content-['Hello_World']">
7. Add borders between horizontal children
   Add borders between horizontal elements using the divide-x-{width} utilities.
8.  Add borders between stacked children
   Add borders between stacked elements using the divide-y-{width} utilities.
9.  focus-within (:focus-within)
   Style an element when it or one of its descendants has focus using the focus-within modifier:
10. 连续修饰符
```
div:has(h2):has(ul) {
  background: black;
} 
```   
1. currentColor  和font color 一致
 
2. target (:target)
 
```
Style an element if its ID matches the current URL fragment using the target modifier:

first (:first-child)   last (:last-child)

only (:only-child)
Style an element if it’s the only child using the only modifier:


empty (:empty)
Style an element if it has no content using the empty modifier:

in-range (:in-range)
Style an input when it’s value is within a specified range limit using the in-range modifier:

<input min="1" max="5" class="in-range:border-green-500 ..." />

```   
1. peer 
   ```
    <input type="email" class="peer ..."/>
    <p class="mt-2 invisible peer-invalid:visible text-pink-600 text-sm">
      Please provide a valid email address.
    </p>
   ```   
2. Style the ::before and ::after pseudo-elements using the before and after modifiers:
   after:content-['*’] after:ml-0.5
3. Justify-end Justify-start
4. Use the border-{side}, border-{side}-0, border-{side}-2, border-{side}-4, or border-{side}-8 utilities to set the border width for one side of an element.

border-x   border-left-width: 1px;border-right-width: 1px;

1. 没有rel=“noopener noreferrer”的情况下使用target=“_blank”是有安全风险，超链接a标签的rel="noopener noreferrer"属性是一种新特性，它能让网站更安全，超链接添加rel="noopener noreferrer"来防止钓鱼网站，因为它获取的window.opener的值为null

1. Use place-content-center to pack items in the center of the block axis: 对应Grid 和 flexbox 
2. Use place-content-stretch to stretch grid items along their grid areas on the block axis:
3. Breakpoint prefix sm 限制了最小值
4. -translate-y-1/2
5. Use inline-flex to create an inline flex container that flows with text.
6. focus:border-blue-400
7. Use contents to create a “phantom” container whose children act like direct children of the parent.
```
<div class="flex ...">
  <div class="flex-1 ...">01</div>
  <div class="contents">
    <div class="flex-1 ...">02</div>
    <div class="flex-1 ...">03</div>
  </div>
  <div class="flex-1 ...">04</div>
</div>
```
1. Sass声明变量必须是『$』开头，后面紧跟变量名和变量值，而且变量名和变量值需要使用冒号：分隔开。

Less 声明变量用『@』开头，其余等同 Sass。

Stylus 中声明变量没有任何限定，结尾的分号可有可无，但变量名和变量值之间必须要有『等号』。

1. 就是当我们对 DOM 结构的修改引发 DOM 几何尺寸变化的时候，会发生回流的过程。
    还有一种情况，是直接合成。比如利用 CSS3 的transform、opacity、filter这些属性就可以实现合成的效果，也就是大家常说的GPU加速。
2. base64 -d  解码  linux 
3. const { name, doubleCount } = storeToRefs(store)  
4. watchEffect 不能检测深层的变化，因此reactive 中变化无效，如果需要则 toRefs 转换
5. V2 $attrs   1. custom events go into a @listerner bucket  2.不能绑定class 
6. Npm ls 查看依赖
7. 可以看到结果reactive是递归会将每一层包装成Proxy对象的，深度监听每一层的property
8. effectScope有一个可选参数为boolean，当传入true时表示阻断与父级的联系，阻断后这个scope对象将不会与父级关联，成为独立的scope。父级的stop也不会影响到它。 
9. Last-Modified,Etag,Expires 三个同时使用时。先判断 Expire ，然后发送 Http 请求，服务器先判断 last-modified ，再判断 Etag ，必须都没有过期，才能返回 304 响应
10. klona  fast utility to "deep clone" Objects, Arrays, Dates, RegExps, and more!
11. Grep string starting with (e.g. 'S’)    grep -o 'S.*’
12. ~: 如果写入的是 〜0.13.0，则当运行 npm update 时，会更新到补丁版本：即 0.13.1 可以，但 0.14.0 不可以。
13. >: 接受高于指定版本的任何版本。
14. ^: 只会执行不更改最左边非零数字的更新。 如果写入的是 ^0.13.0，则当运行 npm update 时，可以更新到 0.13.1、0.13.2 等，但不能更新到 0.14.0 或更高版本。 如果写入的是 ^1.13.0，则当运行 npm update 时，可以更新到 1.13.1、1.14.0 等，但不能更新到 2.0.0 或更高版本。
2. firefox 子元素不缩小需要设置  You need to add min‑width:0
3. flex 布局中子级超过了父级的宽度，需要设置 width:0 ,完全由flex 分配宽度。
4. POSIX stands for Portable Operating System Interface.
5.  @supports CSS at-rule 相当于功能选择器
   ```
   @supports (display: flex) {
  body {
    display: flex;
    min-height: 100vh;
  }
}
   ```
2. https://github.com/cuixiaorui/mini-vue  vue3 source code 

3. react 被 startTransition 回调包裹的 setState 触发的渲染 被标记为不紧急渲染，这些渲染可能被其他紧急渲染所抢占。
   
4. https://hyper.is/ electron console
5. https://cmder.net/ windows 端的console 模拟器
6. Access-Control-Request-Private-Network: true 在所有私有网络预检请求上设置
   Access-Control-Allow-Private-Network: true 必须在所有私有网络预检响应上设置
7. 使用 Fragments，我们不需要在DOM中添加额外的节点。我们只需要用 React.Fragment 或才简写 <> 来包裹内容就行了
8. vite 虚拟模块  虚拟模块是一种很实用的模式，使你可以对使用 ESM 语法的源文件传入一些编译时信息。
9.  glob Match files using the patterns the shell uses, like stars and stuff.
10. click.self 
我们知道在自定义组件上，只能监听自定义事件，一些原生事件（比如click）是没有办法直接触发的，但是使用.native修饰符可以帮我们办到这点
1. offset-path  定义动画运行路径
2. Tauri 是一个为所有主流桌面平台构建小型、快速二进制文件的框架。开发人员可以集成任何编译成 HTML、 JS 和 CSS 的前端框架来构建他们的用户界面。应用程序的后端是一个 Rust 二进制文件，具有前端可以与之交互的 API。
3.  gitsecreat 使用： https://www.mikesay.com/2020/12/16/git-encrypt-file-in-repository/#git-secret%E7%9A%84%E5%AE%89%E8%A3%85%E5%92%8C%E4%BD%BF%E7%94%A8
4. svg2pdf.js 图片转pdf
5. stream 的另外一个模式: objectMode。它是一种对象模式，我们把一件事情、或一个文件、或一个操作，抽象成一个对象。
   ```
   const Readable = require('stream').Readable

   const readable = Readable({ objectMode: true })
    readable.push('a')
    readable.push('b')
    readable.push({})
    readable.push(null)

    readable.on('data', data => console.log(data))

   ```
6. git config --global push.followTags true
7. Markraw 标记不会被reactive
8. watcheffect onInvalidate 在重新运行或者停止的时候执行
9. composedPath() 是 Event 接口的一个方法，当对象数组调用该侦听器时返回事件路径。
10. customref  track and trigger  
11. vueuse useMemoize 对结果加cache
12. elementFromPoint 根据point 获取element
13. Change-case Transform a string between camelCase, PascalCase, Capital Case, snake_case, param-case, CONSTANT_CASE and others.
14. p-retry It does exponential backoff and supports custom retry strategies for failed operations.
15. MutationObserver 观察dom 变化
16. requestFullscreen
17. passive: Boolean，设置为true时，表示 listener 永远不会调用 preventDefault()。如果 listener 仍然调用了这个函数，客户端将会忽略它并抛出一个控制台警告
18. shallowReacive  shallowRef  shallowRef生成非递归响应数据，只监听第一层数据的变化
19. 推荐在大部分时候用 watch 显式的指定依赖以避免不必要的重复触发，也避免在后续代码修改或重构时不小心引入新的依赖。watchEffect 适用于一些逻辑相对简单，依赖源和逻辑强相关的场景（或者懒惰的场景 ）。
20. Object.fromEntries
21. URL.revokeObjectURL() 静态方法用来释放一个之前已经存在的、通过调用 URL.createObjectURL() 创建的 URL 对象。
22. querySelector  返回第一个匹配元素
23. Array.prototype.at()接收一个正整数或者负整数作为参数，表示获取指定位置的成员
24. IFC全称：Inline Formatting Context，名为行级格式化上下文。    触发：块级元素中仅包含内联级别元素
25. The Notification interface of the Notifications API is used to configure and display desktop notifications to the user.
26. TinyMCE 富文本编辑器
27. Window.innerHeight  浏览器窗口的视口（viewport）高度（以像素为单位）；如果有水平滚动条，也包括滚动条高度。
28. vuedraggable 处理拖动数据
29. path-to-regexp   Turn a path string such as /user/:name into a regular expression. The compile function will return a function for transforming parameters into a valid path:
30. vue router 重新render,redirect+fullpath.通过添加一个中转页实现。
31. import { storeToRefs } from "pinia”;
32. html5 input number
 ```
.no-arrow::-webkit-outer-spin-button,
.no-arrow::-webkit-inner-spin-button {
  -webkit-appearance: none;
}
 ``` 
1. vue3 类型 MayBeRef
2. 暂停watch后更新，
```
ignoreUpdates(() => {
  source.value = 'ignored'
})
```
1. dsp 读取json,csv,xlxs 数据
2. limu 创建imutable 对象
3. controlledRef set peek,控制数据的更新
 ```
 const num = controlledRef(0, {
  onBeforeChange(value, oldValue) {
    // disallow changes larger then ±5 in one operation
    if (Math.abs(value - oldValue) > 5)
      return false // returning `false` to dismiss the change
  },
})
 ```

1. flush: post 推迟副作用的初始运行，直到组件的首次渲染完成。
   watch 通过更改设置 flush: 'sync'，我们可以为每个更改都强制触发侦听器，尽管这通常是不推荐的
   ```
- `'pre'`: buffers invalidated effects in the same 'tick' and flushes them before rendering
- `'post'`: async like 'pre' but fires after component updates so you can access the updated DOM
- `'sync'`: forces the effect to always trigger synchronously

 { flush: 'post' }
)

   ```
1. transx vue 动画组件   一个小巧玲珑的 vue 组件切换动画库
2. ts-morph 修改ts 代码，封装后的ts compiler api
3. esno 执行ts
4. https://mermaid-js.github.io/mermaid/#/     mermaid 及其方便的画图工具
5. vue-parallaxy Is a compontent for fast 60fps parallax scroll effects in vue 2. 实现滚动的视差效果。
6. useWatermark,Layzcontainer. context menu  vue-vben-admin 中
7. localForage is a fast and simple storage library for JavaScript。Wraps IndexedDB, WebSQL, or localStorage using a simple but powerful API.
8.  markRaw 标记对下不会被reactive
9.  indexeddb-fs is a module that allows you to store data in the browser using an API similar to that of Node's fs module.
10. 临时安全令牌（Security Token Service，STS）
11. *** 获取文本px宽度* @param font{String}: 字体样式**

```
String.prototype.pxWidth = function(font) {
  // re-use canvas object for better performance
  var canvas = String.prototype.pxWidth.canvas || (String.prototype.pxWidth.canvas = document.createElement("canvas")),
      context = canvas.getContext("2d"); 

  font && (context.font = font);
  var metrics = context.measureText(this);

  return metrics.width;
}
```

1. 先保存各个实例的values信息， helm get values [release] > xxx.yaml


1. 
HTTP协议中用头部字段Accept-Encoding 和 Content-Encoding对「采用何种编码格式传输正文」进行了协定，请求头的Accept-Encoding会列出客户端支持的编码格式。当响应头的 Content-Encoding指定了gzip时，浏览器则会进行对应解压

1. Transfer-Encoding，是一个 HTTP 头部字段，字面意思是「传输编码」。实际上，HTTP 协议中还有另外一个头部与编码有关：Content-Encoding（内容编码）。Content-Encoding 通常用于对实体内容进行压缩编码，目的是优化传输，
```
Transfer-Encoding: chunked
Transfer-Encoding: compress
Transfer-Encoding: deflate
Transfer-Encoding: gzip
Transfer-Encoding: identity
```


2. 逐跳消息头  这类消息头仅对单次传输连接有意义，不能通过代理或缓存进行重新转发

 
2. mime  https://github.com/sindresorhus/file-type  根据文件内容判断类型

1. 语义化版本控制(SemVer)
   先简单了解下什么是语义化的版本控制，其是由GitHub发起的一份用于规范版本号递增的规则，

1.  deeplinks.js allows people to easily link directly to any text selection on your website.
2.  Vue DevUI 开源的UI
3. standard-version
standard-version 会根据提交的信息类型来自动更改对应的版本号,如下:
```
feat: 次版本(minor)+1
fix: 修订号(patch) +1
BREAK CHANGE: 主板号(marjor) +1
```
1. outline 能告诉用户那一个可以激发事件的html元素获取了焦点，对钟爱键盘操作的用户尤其有意义。一个清晰悦目的outline设计能提高使用表单的用户体验。
2. CSS属性 columns 用来设置元素的列宽和列数。
重点，设置了display: contents的元素本身不会被渲染，但是其子元素能够正常被渲染。
3. 为了使我们的盒子居中，通过align-items属性，可以将交叉轴上的item对齐，此时使用的是垂直方向的块轴。而使用justify-content则可以对齐主轴上的项目，主轴是水平方向的。
align conent  用来控制多行布局   控制“多条主轴”的 flex 项目在交叉轴的对齐。

1. CSS 中的 place-items 是一个简写属性 ，它允许你在相关的布局（如 Grid 或 Flexbox）中可以同时沿着块级和内联方向对齐元素 (例如：align-items 和 justify-items 属性) 。如果未提供第二个值，则第一个值作为第二个值的默认值

1. filter CSS属性将模糊或颜色偏移等图形效果应用于元素。滤镜通常用于调整图像，背景和边框的渲染。

1. monaco 自定义language
```
register monaco.languages.register({ id: 'mySpecialLanguage' });
setMonarchTokensProvider base language 里面有3 
defineTheme  设置样式
monaco.editor.defineTheme('myCoolTheme', {
                    colors: {},
                    base: 'vs',
                    inherit: false,
                    rules: [
                        { token: 'custom-info', foreground: '808080' },
                        { token: 'custom-error', foreground: 'ff0000', fontStyle: 'bold' },
                        { token: 'custom-notice', foreground: 'FFA500' },
                        { token: 'custom-date', foreground: '008800' }
                    ]
                });
registerCompletionItemProvider  智能提示，遇到对应的关键词
```

1. Monarch  用来实现代码高亮   https://juejin.cn/post/6844903736867831822

https://microsoft.github.io/monaco-editor/monarch.html

1. xe-utils 提供工具类
1. Mitt  Tiny (~200b) functional event emitter / pubsub.
1. element-resize-detector  
1. memoize-one 记录最近的返回结果,不同参数会重置
1. 钱其实是“保健因子”，而不是“激励因子”，是多了没用、少了不行的东西
2. 可以看到整个医改的核心就是放供给、促竞争和扶创新的过程
3. 破船能过河
4. Comlink Comlink makes WebWorkers enjoyable. 多线程
5.  
`Rails-style`: 按照文件的类型划分为不同的目录

`Domain-style`: 按照一个功能特性或业务创建单独的目录

`Ducks-style`: 优点类似于Domain-style，不过更彻底, 它通常将相关联的元素定义在一个文件下·

1. 
    强约定，体现团队的规范。首先它应该避免团队成员去关心或更改构建的配置细节，暴露最小化的配置接口。 另外构建工具不仅仅是构建，通常它还会集成代码检查、测试等功能。

    方便升级。尤其是团队需要维护多个项目场景, 这一点很有意义

2. BEM
```
元素（Element），即 price 、text ，代表从属于某个块，是这个块的子元素，跟在块后面，以双下划线为间隔，使用 .btn__price 、.btn__text 表示

修饰符（Modifier），即 orange 、big ，用于修改块的状态，为块添加特定的主题或样式，跟在块后面，以双连字符为间隔，使用 .btn--orange 、.btn--big 表示

```   
1.  npm-run-all
```
Before: npm run clean && npm run build:css && npm run build:js && npm run build:html
After: npm-run-all clean build:*
```

1. display:flow-root可以让元素块状化，同时包含格式化上下文BFC，可以用来清除浮动，去除margin合并，实现两栏自适应布局等。

1. stroke-dash 是一个定义虚线和间距图形的图像工具类, 被用于轮廓描边;

1. npx degit
   
1.  有一些环境变量，比如HOME、PATH、SHELL、UID、USER等，在用户登录之前就已经被/bin/login程序设置好了。通常环境变量被定义并保存在用户家目录下的．bash_profile文件或全局的配置文件/etc/profile中

1. env命令只显示全局变量；declare命令输出所有的变量、函数、整数和已经导出的变量

1. http upgrade 通常来说这一机制总是由客户端发起的 （不过也有例外，比如说可以由服务端发起升级到传输层安全协议（TLS））， 服务端可以选择是否要升级到新协议。借助这一技术，连接可以以常用的协议启动（如HTTP/1.1），随后再升级到HTTP2甚至是WebSockets.

1. 因为 CommonJS 在运行时进行加载方式的动态解析，在运行时阶段才能确定的导入导出关系，因此无法进行静态编译优化和类型检查。​

1. JSZip  JSZip is a javascript library for creating, reading and editing .zip files, with a lovely and simple AP
   
2. spy-debugger  一站式页面调试、抓包工具。远程调试任何手机浏览器页面，任何手机移动端webview（如：微信，HybridApp等）。支持HTTP/HTTPS，无需USB连接设备
   
3. viteshot 基于vite 的快照

4. useScrollLock

