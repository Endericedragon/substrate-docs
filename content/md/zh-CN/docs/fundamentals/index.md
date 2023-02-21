---
标题：基础知识
简介：为您介绍基于Substrate的区块链所遵循的核心准则和独特的功能特性，以及Substrate运行时开发。
章节：文档
关键词：
  - 区块链
  - 共识
  - substrate
  - 架构
---

基础知识章节的话题将围绕Substrate开发环境的核心准则和独特功能特性展开；此外，我们也将强调数个可供区块链开发者选择的设计选项。

Substrate提供了一组模块化的、灵活的工具库，为您在开发不同特定用途的区块链时随意选择、组合、修改并复用。无论是在私有网络中运行，抑或是经由Polkadot与其他区块链联动，Substrate均能胜任。

本章的话题将帮助您了解：通过Substrate能够搭建起什么样的区块链系统？这些系统能够贴合您的实际需求的秘诀又何在？

Before you start building, though, you want to make sure you are in the right place.

在我们正式使用Substrate开始开发之前，请您了解以下板块的知识：

- [区块链基础](/fundamentals/blockchain-basics/) 向您解释了开发区块链系统的复杂程度，并介绍了常见的区块链概念、组件和术语。

- [为何选择Substrate？](/fundamentals/why-substrate/) 强调了Substrate所提供的，其他大部分区块链与智能合约平台所不具有的关键优点。

- [Substrate是什么？](/fundamentals/what-is-substrate/) 解释了Substrate设计背后的核心理念，以及设计决策对我们使用的技术的影响。

- [架构](/fundamentals/architecture/) 描绘了Substrate中节点架构的关键组件，以及这些组件如何与您自己的个性化区块链设计架构相关联。

- [网络与区块链](/fundamentals/node-and-network-types/) 定义了在不同区块链部署场景下的不同拓扑结构，以及它们在基于Substrate的区块链中的实现。

- [运行时开发](/fundamentals/runtime-development/) 强调了Substrate运行时的重要性，介绍了Substrate运行时的核心应用接口和运行之的最低要求。

- [共识](/fundamentals/consensus/) 介绍最常见的共识模型，以及您能够在Substrate区块链上使用的共识模型的种类。

- [交易与区块基础](/fundamentals/transaction-types/) 介绍交易的种类，以及构成一个区块的组件。

- [交易周期](/fundamentals/transaction-lifecycle/) 介绍交易是如何被接收、排队处理，并最终封装进区块的。

- [状态转换与存储](/fundamentals/state-transitions-and-storage/) 描述在运行时中，状态如何转换与存储，以及使用字典树和键值对加以管理。

- [账户、地址与密钥](/fundamentals/accounts-addresses-keys/) 介绍了账户、地址与密钥的相互关系以及它们的用途。

- [为Substrate所用的Rust](/fundamentals/rust-basics/) 强调了Rust特有的traits（特征）、泛型，关联类型和宏。熟练掌握这些知识，您就能顺利第构建基于Substrate的区块链了。

- [离链操作](/fundamentals/offchain-operations/) 揭示了一部分操作最好离链操作的原因，以及它们的平替。

- [Substrate连接中的轻量级客户端](/fundamentals/light-clients-in-substrate-connect/) 介绍了使用Substrate连接在您的应用程序中嵌入一个轻量级客户端的方法，以与其他基于Substrate的链互交互。

- [跨共识通信](/fundamentals/xcm-communication/) 一份有关跨共识通信及其通信格式的概述。

在您消化了以上章节的知识之后，您就已经完全准备好设计、构建、测试属于您的区块链了。

