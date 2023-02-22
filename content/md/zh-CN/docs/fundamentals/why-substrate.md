---
标题：为何选择Substrate？
简介：本章介绍与其他区块链和智能合约平台不同的Substrate开发环境的核心优势。
关键词：
  - 视图（vision）
  - 智能合约
  - 运行时开发
  - 区块链
  - 共识
  - substrate
  - 架构
---

进行区块链开发非常复杂。您必须正确掌握一系列复杂的技术（例如高级密码学和分布式网络通信），以便为应用程序运行和用户信任提供一个安全的平台。在拓展性、管理、组件间协作和可升级性，都是程序员需要面对的难题。这种复杂性为开发人员创造了一个相当高的门槛。

既然如此，我们不禁想问出第一个问题：我们到底想构建一个什么东西？

Substrate并非放之四海而皆准的万金油，但如果您想构建这样的项目，那Substrate大概率是您的最佳选择：

-   您的项目用途具有很高的特殊性
-   您的项目需要和其他区块链互动
-   您的项目涉及到预定义的、可组合的模块化组件
-   您的项目需要拥有随着时间升级的能力

Substrate is a Software Development Kit (SDK) specifically designed to provide you with all of the fundamental components a blockchain requires so you can focus on crafting the logic that makes your chain unique and innovative.

Substrate是一个软件开发工具包（SDK），它能为您提供构建区块链所需的所有基本组件，您只需专注于制作使您的链独特和创新的逻辑即可。

和其他的分布式账本不同的是，Substrate具有以下特点：

- [灵活](#flexible)
- [开源](#open)
- [可协作](#interoperable)
- [可升级](#future-proof)
- [可衔接的（Where to go next）](#where-to-go-next)

## 灵活

大多数区块链平台都有非常紧密耦合的子系统，并且很难解耦。倘若其中的某几个子系统存在风险，这些难以发现的耦合可能严重破坏区块链系统本身。

相比之下，Substrate是一个完全模块化的区块链框架，通过选择适合您的项目的网络堆栈、共识模型或管理方法或创建自己的组件，您可以使用显式解耦的组件组成一个链。有了Substrate，您可以部署根据您的规范设计和构建的区块链，但它也可以随着您不断变化的需求而发展。

## 开源

所有的Substrate体系结构和工具都可在遵循[开源许可协议](https://github.com/paritytech/substrate#license)的前提下使用。Substrate框架的核心组件均使用像`libp2p`和`jsonRPC`这样的开源协议，并且允许您决定如何定制您的区块链架构。

Substrate也有一个活跃、乐于助人的大型[构建者社区](https://substrate.io/ecosystem/)，源源不断地为软件生态做出贡献；这些贡献允许您在开发自己的区块链时，向其引入新的增强功能。

## 可协作

大多数区块链平台与其他区块链网络的交互能力有限。与之不同的是，所有基于Substrate的区块链都可以通过[跨共识消息传递](https://wiki.polkadot.network/docs/learn-crosschain) (XCM)与其他区块链进行互操作。

Substrate可用于创建作为独立网络（单链）的区块链，或与[中继链](https://wiki.polkadot.network/docs/learn-architecture#relay-chain)紧密耦合以作为[平行链（parachain）](https://wiki.polkadot.network/docs/learn-parachains)共享其安全性。

## 可升级

Substrate为可升级、可组合和可适应性而生。

状态转换逻辑（Substrate运行时，下称运行时）是一个自包含的WebAssembly对象，而您的节点拥有在特定条件下完全改变运行时本身的能力，从而在网络范围内进行运行时升级。因此，“无分叉”升级（forkless upgrades）是可能的，因为在大多数情况下，节点不需要任何操作就可以使用这个新的运行时。随着时间的推移，网络的运行时协议可以无缝地（也许是根本地）随着用户的需求而发展。

## 下一步学什么？

Substrate提供了一套用于构建区块链和链上应用程序的、独树一帜的强力框架。

- 您可以从一个预定义的节点入手，启动一条没有节点的单链
- 您可以使用Substrate构建一条独立于其他区块链的定制单链
- 您可以将您的Substrate区块链耦合入一条接力链，例如Polkadot或者Kusama

根据您的知识储备和兴趣点，您可选择参阅以下链接：

#### 请告诉我更多！

- [区块链基础](/fundamentals/blockchain-basics/)
- [架构](/fundamentals/architecture/)
- [运行时开发](/fundamentals/runtime-development)
- [网络与区块链](/fundamentals/node-and-network-types/)
- [安装](/install/)

#### 请引导我实践！

- [搭建本地链](/tutorials/get-started/build-local-blockchain/)
- [模拟网络](/tutorials/get-started/simulate-network/)
- [添加可信的验证器](/tutorials/get-started/add-trusted-nodes/)

若您偏爱直接上手研究代码，请移步[Substrate Playground](https://docs.substrate.io/playground/)或者参阅[API参考信息](https://paritytech.github.io/substrate/master)，以了解您将使用的Rust crates。

