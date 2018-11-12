---
title: "Home Bank"
date: 2018-11-11T08:50:09-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

The entire Taiji Blockchain is sharded up to 10000 subchains, and partners we call banks will operate all subchains except the first three chains with Id (0000, 0001 and 0002). 

When you join the Taiji Blockchain, chances are you have an account with one of the partners. They will give you a client application to generate a wallet and the address generated will start with four digits match to the [chainId][] the partner is operating. When you send coins or tokens to others, you always post the transaction to the instance maintained by the organization who provide the client application. This organization is a bank, and it is your home bank. 

We have general guidelines on transaction fees and services provided by each bank; however, as these banks operate on different geolocation, they need to have the flexibility to change the rules. 

For example, we have a cap for the inner chain transaction fee to support partner bank operation, but they might decide to reduce the fee to attract more users to their subchain. The more users are there, the more transactions will be performed by that node, and the total transaction fee might be higher. 

[chainId]: /concept/chain-id/
