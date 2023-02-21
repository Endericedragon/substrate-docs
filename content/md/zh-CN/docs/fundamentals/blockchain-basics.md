---
标题：区块链基础
简介：介绍了常见的区块链概念、组件和术语。
关键词：
  - 区块链
  - 区块
  - 共识
  - 状态机
  - 局限性（limitations）
---

区块链是一个去中心化的分布式账本，它以一系列的区块记录信息。区块包含的信息是一组有序的指令集合，这些指令可能导致状态的变化。

在区块链网络中，各个计算机（称为节点）相互通信，形成了去中心化的点对点（P2P）网络。在这样的网络中，并不存在所谓中央权威机构控制；每个参与区块生成的节点，都存储着组成所有节点公认的区块链区块的副本。

多数情况下，用户通过提交请求来与区块链交互，这些请求可能导致区块链的状态转变。例如，一个请求可能改变一份文件的所有权，或者在两个账户之间转移资产。这些交易请求将由网络中的其他节点传播，并由区块生产者（block author）封装成一个区块。

为了确保链上数据的安全性和链上正在进行的事务的进度，节点使用某种形式的共识，就每个区块中的数据状态和已完成执行的事务的顺序达成一致。

## 什么是区块链节点？

抽象至一定高度后，所有的区块链节点都可以认为由以下四部分组成：

- 数据存储区，它们记录交易之后产生的不同状态
- 点对点网络，用于去中心化地与其他节点通信
- 共识算法，用于保护自己免受恶意攻击者的攻击，确保链上事务顺利执行
- 为收到的交易进行排序、处理的算法逻辑
- 加密算法，用于为区块生成哈希摘要，为交易进行签名，以及验证收到的交易的签名

由于搭建区块链系统所需的核心组件的实现复杂度非常大，大多数区块链项目都是基于一份现成的代码作为基础，这样一来，程序员就可以通过修改已有代码来增添新功能，而非自己从零实现一个了。

例如，Litecoin、ZCash、Namecoin和Bitcoin Cash都是从比特币的代码仓库中fork出去的。相似地，Quorom，POA Network，KodakCoin和Musicoin是从以太坊的代码仓库fork出去的。

然而，大多数区块链平台并不是为个性化定制区块链而准备的。其结果就是，仅仅通过fork已有的仓库来构建新区块链有非常严重的局限性，包括但不限于原区块链代码带来的可延展性差等问题。

在我们探索Substrate在区块链项目中缓解上述问题的妙招之前，您很有必要了解一些大部分区块链共有的常见属性。通过学习大部分区块链的操作方法，您将更好地了解Substrate如何为构建最适合您需求的区块链提供替代方案和功能。

## 状态转换与冲突

区块链的本质是[状态机]((https://en.wikipedia.org/wiki/Finite-state_machine))。

在状态机运行的任意时刻，它都拥有一个内部的状态。

当执行收到的交易时，它们会导致状态的更改，因此区块链必须从当前状态转换到新状态。

但是，可能存在多个有效转换，这些转换将导致不同的新状态，区块链必须在其中选择一个，使之可以与其他节点产生共识。

为了就状态转换之后的新状态达成共识，所有区块链中的操作都必须是确定的。为使链能够正常运转，居多数的节点必须就状态转换之后的新状态达成共识，这包括：

- 这条链的初始状态，又被称作“创世状态”或者“创世区块”
- 每一块区块中记录的，因发生交易而产生的状态变化
- 链中即将加入的，最终的状态

在中心化的网络中，“中心权威机构”可以在互斥状态转换之间进行选择。例如，配置为主要授权机构的服务器可能会按照看到它们的顺序，记录状态转换的更改；或者在冲突发生时，使用加权的算法在相互冲突的方案之间进行选择。

区块链用于将事务批量处理成区块并选择哪个节点可以向链提交区块的方法，称为区块链的共识模型或共识算法。最常用的共识模型被称为工作量证明共识模型。在工作量证明共识模型中，第一个完成计算问题的节点才有权向链提交区块。

为了使区块链具有容错能力并令所有节点拥有一致的状态，一些共识模型要求：即使某些节点受到恶意行为者干扰或网络中断威胁，至少三分之二的节点也必须在任何时候都对状态达成一致。

这三分之二的多数节点确保了网络是容错的，并且可以承受一些网络参与者的不良行为，无论这些行为是故意的还是偶然的。

## Blockchain economics

All blockchains require resources—processors, memory, storage, and network bandwidth—to perform operations.
The computers that participate in the network—the nodes that produce blocks—provide these resources to blockchain users.
The nodes create a distributed, decentralized network that serves the needs of a community of participants.

To support a community and make a blockchain sustainable, most blockchains require users to pay for the network resources they use in the form of transaction fees.
The payment of transaction fees requires user identities to be associated with accounts that hold assets of some type.
Blockchains typically use tokens to represent the value of assets in an account and network participants purchase tokens outside of the chain through an exchange.
Network participants can then deposit the tokens to enable them to pay for transactions.

## Blockchain governance

Some blockchains allow network participants to submit and vote on proposals that affect network operations or the blockchain community.
By submitting and voting on proposals—referenda—the blockchain community can determine how the blockchain evolves in an essentially democratic process.
On-chain governance is relatively rare, however, and to participate, a blockchain might require users to maintain a significant stake of tokens in an account or to be selected as a representative for other users.

## Applications running on a blockchain

Applications that run on a blockchain—often referred to as decentralized applications or dApps—are typically web applications that are written using front-end frameworks but with backend **smart contracts** for changing the blockchain state.

A smart contract is a program that runs on a blockchain and executes transactions on behalf of users under specific conditions.
Developers can write smart contracts to ensure that the outcome of programmatically-executed transactions is recorded and can't be tampered with.
Yet, with smart contracts alone, developers don't have access to some underlying blockchain functionality—such as the consensus, storage, or transaction layers—and instead, abide by a chain's fixed rules and restrictions.
Smart contract developers often accept these limitations as a tradeoff that enables faster development time with fewer core design decisions to make.

## Where to go next

All blockchains share some common characteristics.
Substrate—while not a blockchain itself—is a blockchain builders' toolkit with a modular framework of components to create a custom blockchain.
With Substrate, you can take the common blockchain components—like storage and consensus and cryptography—and combine them to use the functions they provide as-is or modify them to suit the purpose of your project.

You can explore the following resources to learn more.

#### Tell me

- [Fundamentals](/fundamentals/)
- [Why Substrate?](/fundamentals/why-substrate/)
- [Architecture](/fundamentals/architecture/)
- [Networks and blockchains](/fundamentals/node-and-network-types/)

#### Guide me

- [Build a local blockchain](/tutorials/get-started/build-local-blockchain/)
- [Simulate a network](/tutorials/get-started/simulate-network/)
- [Add trusted nodes](/tutorials/get-started/add-trusted-nodes/)

If you prefer to explore code directly, you can start building in the [Substrate Playground](https://docs.substrate.io/playground/) or consult the API reference to get details about the Rust crates you use.
