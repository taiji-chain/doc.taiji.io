---
title: "Initial Performance"
date: 2018-10-28T23:13:15-04:00
description: "Initial performance result on my desktop"
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

We are building a blockchain on top of the light platform with our experience on high performance distributed applications. Today we've done an initial performance test for transactions on my i5 desktop, and the numbers look very good. 2.8K requests per second and each request have one credit entry and one debit entry.

The test is against one chain-writer server which should be installed in a bank or government. Currently, there are three sharded chains with addresses started by 0000, 0001 and 0002. 

```
Africa: '0002'
Asia: '0001'
Americas: '0000'
Europe: '0002'
Oceania: '0001'
```

```
steve@joy:~/light-chain/chain-writer$ wrk -t2 -c400 -d30s -s post.lua https://localhost:8443/transaction/taiji
Running 30s test @ https://localhost:8443/transaction/taiji
  2 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   147.43ms  103.40ms 977.65ms   73.48%
    Req/Sec     1.45k   338.81     2.99k    75.98%
  84315 requests in 30.09s, 6.92MB read
Requests/sec:   2802.37
Transfer/sec:    235.36KB
```

With more partners join the network, we can easily handle millions of transactions per second. The next step is to build a web client for the end user to interact with chain-writer service. 
