---
title: "Snapshot"
date: 2018-12-20T17:12:49-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
reviewed: true
---

The current taiji-blockchain implementation is based on Kafka 2.6.0, and the transactions are persisted into a topic called taiji, which is partitioned. Each subchain is a partition and managed by a home bank. All ledger entries are written to the taiji topic in transactions so that the data is consistent across all partitions for debits and credits. 

For each partition, a corresponding service called chain-writer is responsible for safeguarding the particular partition. 

To prevent double-spending, the chain-writer will maintain an in-memory snapshot with each address's balance for the subchain. As all addresses in the snapshot belong to the same home bank, and all debit actions will happen on the same chain-writer instance, we are sure that the in-memory snapshot balance is less than the real balance. The incoming credit amount from another subchain/partition is not in the in-memory snapshot as another instance of chain-writer updates the ledger. 

Running in parallel, we have snapshot streams that aggregate all transactions into a key/value store and, finally, snapshot topic per chain-reader instance. The chain-reader will use the key/value store to serve the queries from clients. 

It doesn't make sense for a chain-writer to scan the entire currency topic to derive the in-memory snapshot every time it restarts. I will load the initial in-memory image from the snapshot topic. Once the server is up and running, it also subscribes to the currency topic to update the in-memory snapshot when necessary. The only time that an in-memory snapshot needs to be updated is that there is a credit entry, and the from address doesn't belong to the current partition. 

In order for the consumer to start from the right offset in the current topic, we need to know the offset the last snapshot is processed. To do that, we have put the offset into the snapshot data. Its key is the wallet address, and value will be currency and "balance offset partition" map. 

Once the in-memory snapshot is loaded from the snapshot topic, it will move to the currency topic to start from the last offset marked in the snapshot to check if the subsequent record needs to update the in-memory snapshot. 

