---
title: "ERC20 Token"
date: 2018-11-12T19:35:05-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
reviewed: true
---

It is the first application we want to provide as we need a light token to attract people to help the Light Platform and Taiji Blockchain community. For every contribution, we are going to pay with a certain amount of LIGHT tokens. The token doesn't have any monetary value, and it represents the value each contributor brings to the community. The tokens can be transferred to any valid address, and we reserve the right to convert these tokens with cryptocurrencies or fiat currencies in the future. 

With a tiny fee, everyone can create their own security tokens and grant to other address to withdraw or transfer to different address from the owner. 

The token can also be used for authentication and authorization to access distributed applications. For example, you have to hold a specific token in order to vote in a city election. Once you have voted, the token will be spent, and you cannot vote again. 

To try the token application, please create wallet, populate 1000 taiji coins and create your token on the [demo web-client][]. 

### TokenCreatedEvent

Create a new token that is identified by a generated entity address. The token can also be identified by a symbol you pick. 

### TokenApprovedEvent

If you are a token holder, you can approve another address to withdraw tokens up to the approved amount. 

### TokenTransferredEvnet

If you are a token holder, you can transfer a certain amount of tokens to another address.

### TokenWithdrewEvent

Once you have the approval from another address for a token, you can withdraw it. 

### TokenInfo

Get all tokens available on the blockchain or a particular token by address or symbol. 

### TokenAccount

Query token account info by an address. Optionally, you can specify a token address or symbol to query holdings for that particular token. 

### TokenTransaction

Get all the token transactions for an address. If a token address or a symbol is provided as an additional query field, then the result will be filtered by that token only. 

[demo web-client]: https://demo.taiji.io
