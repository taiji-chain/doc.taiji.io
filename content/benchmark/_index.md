---
title: "Benchmark Overview"
date: 2018-11-06T11:16:05-05:00
description: "Benchmark of Taiji Blockchain"
categories: []
keywords: [benchmark]
menu:
  docs:
    parent: "benchmark"
    weight: 1
weight: 1
aliases: []
toc: false
draft: false
---

Taiji Blockchain is based on a partitioned distributed append-only log for transactions, and it is infinitely scaling. Each subchain can support about 2800 transactions per second on my aging desktop computer with all components running on the same machine. When the workload split to multiple physical machines, each subchain should support at least 200K transactions per second. For the public chain, we are planning to have up to 10K subchains, and you can imagine how many transactions it can support in a second. 

The chain-writer and chain-reader services are built on the [light-4j][] platform, and it is [one of the fastest microservices platforms][]. 


Here is the performance test from my desktop with an i5 CPU. 

```
wrk -t2 -c400 -d30s -s post.lua https://localhost:8443/transaction/taiji
Running 30s test @ https://localhost:8443/transaction/taiji
  2 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   147.43ms  103.40ms 977.65ms   73.48%
    Req/Sec     1.45k   338.81     2.99k    75.98%
  84315 requests in 30.09s, 6.92MB read
Requests/sec:   2802.37
Transfer/sec:    235.36KB
```

[light-4j]: https://www.networknt.com/
[one of the fastest microservices platforms]: https://github.com/networknt/microservices-framework-benchmark


