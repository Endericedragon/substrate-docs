---
标题：架构
简介：介绍一个Substrate节点的核心组件。
关键词：
---

正如我们在[区块链基础](/fundamentals/blockchain-basics)一章中所说，一个区块链依赖于去中心化的网络，在网络中，数台电脑（亦称为节点）之间可以相互通信。

由于任意区块链中必然包含节点这一核心概念，我们有必要了解让Substrate节点之于其他普通节点的独到之处，例如默认提供的核心服务和库，以及改造并拓展节点使之适用于多种工况的方法。

## 高层次概述

在一个去中心化的网络中，所有的节点不仅充当客户端（向网络请求数据），也能发挥服务器的作用（对网络请求作出响应）。从概念上来说（同时也可以从编程的角度来说），Substrate架构也按照类似的方式划分节点的操作职责。

下图简要说明了这种职责的划分，以帮助您直观了解Substrate架构，以及Substrate如何为构建区块链提供模块化框架。

![Substrate architecture](/media/images/docs/simplified-architecture.png)

高层次概括地说，Substrate节点提供了一个层次化的环境，其中包含两个主要的元素：

- 一个带有**外部节点服务**（outer node services）的**客户端**，用于处理网络活动，如发现对等节点、管理交易请求、与对等节点达成共识以及响应RPC调用。

- 一个包含了执行区块链的状态转换函数的所有业务逻辑的**运行时**。

### 外部节点

外部节点负责运行时外部发生的活动。例如，外部节点负责发现对等节点、管理交易池、与其他节点通信以达成共识，以及响应来自“外部世界”的RPC调用或浏览器请求。

外层节点处理的一些最重要的活动包括以下几种：

- [存储](/fundamentals/state-transitions-and-storage/): 使用简单高效的键值对存储层，保存Substrate区块链不断变化的状态。

- [点对点网络](/fundamentals/node-and-network-types/): 使用[libp2p` network stack](https://libp2p.io/)的Rust实现与其他的网络参与者通信。

- [共识](/fundamentals/consensus/): 与其他网络参与者通信，以确保他们对区块链的状态达成共识。

- [Remote procedure call（RPC） API](/build/remote-procedure-calls/): 接收入站的HTTP和WebSocket请求，以便区块链用户与网络交互。

- [维护节点度量](/maintain/monitor/): 通过内嵌的[Prometheus](https://prometheus.io/)服务器收集并提供节点度量相关的信息。

- [执行环境](/build/build-process/): 为运行时选择要使用的执行环境（WebAssembly或本地的Rust）然后将调用分派给所选的环境。

执行这些任务通常需要外部节点查询运行时以获取信息或向运行时提供信息。这种通信通过调用专门的[runtime APIs](/reference/runtime-apis/)来处理。

### 运行时

运行时确定交易是否有效，并负责处理区块链的状态转换函数的更改。因为运行时能执行它接收到的函数，所以它可以控制如何将交易包含在区块中，以及如何将区块返回到外部节点以传播或导入到其他节点。从本质上讲，运行时负责处理区块链上发生的所有事情，它也是构建Substrate区块链节点的核心组件。

Substrate运行时被设计成编译为[WebAssembly (Wasm)](/reference/glossary#webassembly-wasm)字节码的形式。这样的设计决策有如下益处：

- 支持无分叉的升级。
- 多平台适配。
- 可以检查运行时有效性。
- 已验证可用于中继链共识机制。

与外部节点向运行时提供信息的方式类似，运行时使用专门的[主机函数（host function）](https://paritytech.github.io/substrate/master/sp_io/index.html)与外部节点或外部世界通信。

## 轻量级（light）客户端节点

轻量级客户端或轻量级节点是Substrate节点的简化版本，仅提供运行时和当前状态。它允许用户使用浏览器、浏览器扩展、移动设备或家用电脑直接连接到Substrate运行时。

有了轻量级客户端节点，您就可以使用用Rust、JavaScript或其他语言编写的RPC端口（endpoint）连接到WebAssembly执行环境，以读取区块头（block header）、提交交易并查看其的结果。

## 下一步学什么？

在您已经对Substrate体系结构和核心节点组件有了基本的认知后，我们建议参阅以下主题以了解更多信息：

- [网络和区块链](/fundamentals/node-and-network-types)
- [交易和区块基础](/fundamentals/transaction-types)
- [交易生命周期](/fundamentals/transaction-lifecycle/)
- [状态转变和存储](/fundamentals/state-transitions-and-storage/)
- [Runtime APIs](/reference/runtime-apis/)
