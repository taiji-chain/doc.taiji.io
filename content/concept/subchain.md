---
title: "Subchain"
date: 2018-11-12T17:54:46-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---


Most public blockchains started with one chain, and they think about scalability when they hit the bottleneck. We begin with the distributed partitions to divide the Taiji Blockchain to multiple subchains. Each subchain has a [chainId][] which is four digits number. All addresses belong to that subchain starts with those four digits. 

A virtual bank will own a subchain and operate it. We normally select partners to operate as virtual banks based on geolocation. In this case, we can be relatively confident that most local transactions will be [inner-chain transaction] which is more efficient. 

[chainId]: /concept/chain-id/
[inner-chain transaction]: /concept/inner-tx/