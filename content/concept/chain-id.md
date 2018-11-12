---
title: "Chain Id"
date: 2018-11-11T08:49:56-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

Most public blockchains have only one chain, and all transactions are saved into the blocks in that chain. There is only one chain writer for the current block, and all transactions compete with each other to write into the current block in a mining process. The result is that most cryptos can only support several to dozens of transactions per second.

Taiji-chain is sharded to multiple subchains or partitions up to 10000. Each subchain has an Id which is four-digit numbers from 0000 to 9999. In the beginning, we only have three subchains 0000, 0001 and 0002 and our parent company Network New Technologies Inc. operates all three of them. Our partners who we call them banks will operate other subchains in the future. 

The first three subchains are allocated based on the geolocation from our users. 

- 0000 Americas
- 0001 Asia and Oceania
- 0002 Europe and Africa

When you create your wallet, you will be asked to select the subchain based on your geolocation. Your generated address will be started with the corresponding four digits. 

When you start a transaction signed by your address, the transaction will be routed to the chain-writer instance that is responsible for that subchain. 

When you use the generic client comes with [taiji-blockchain][], you can choose the subchain on your own. In the future, if your [home bank][] offer you a customized client to create a wallet, the address should always belong to the same subchain operated by the home bank. 


[light-blockchain-4j]: https://github.com/networknt/taiji-blockchain
[home bank]: /concept/home-bank/


