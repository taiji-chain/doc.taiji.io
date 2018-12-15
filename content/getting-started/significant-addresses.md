---
title: "Significant Addresses"
date: 2018-12-15T12:52:05-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---


This page listed all the significant addresses for the blockchain. These addresses are used by the testnet and maybe used by the mainnet as well. 

### Root Address

Root address is used to populate all currency supply in the genesis block. It is the initial value written into the blockchain without any application running. It is the only data written into the blockchain without any validation. 

Once the fund is moved to the root address, this root address is retired. It contains nothing and nobody can access it. Please don't send any coin to this address. 

```
00008cc1124819F5Aa5f9944b4D79b7d8ee615e3
```

### Seed Address

There is only one seed address, and it holds the total supply of the currency after all blockchain services are up and running. After the currencies distributed to the 10 head addresses, it would be retired and shouldn't be used. Please don't send any currency to this address.

```
000085DF3b608aF058482391681C3a04C437776C
```

### Head Addresses

Ten header addresses hold all the currencies. Four addresses belong to the home bank 0000, three addresses belong to the home bank 0001, and three addresses belong to the home bank 0002. 

You can query the balance for these addresses. 

```
000002c4a747cA60517d9db0033526d5052e1B48
00009512b85E10Dd5fAA495757FaFa72e198a56b
00002308B975C9e08CAfCb2C343D9c71faaf8021
0000c1106217e68802d41406642A68e628fD7f97

00012A20B14156c02e09a45d978BE7e00030fD0a
0001D20Ca248a2BB7e1c6cB4654B3fe15b1Dc246
0001a01963b09fe09DE62d83BD2B9A0c2b618D74

00027539AF078DB873106c9c3adC728A1AF8d040
0002416c287a6Ef2aa20692E72521B2b79917175
0002BEFf9A0eAD7026A42aDe3FF008cD46e5B2A5

```

### Faucet Address

Faucet address is only available for the testnet as it is the way to populate newly created wallet. 


```
0000Ff14aD21d03D20b7eE96d031552cf9dD9072
```


### Distribution Addresses

In the genesis block, we populate some of the addresses for our investors and community contributors. For the testnet, you can find the following addresses for testing. 

```
00000A3A878440702AbC03d4424d979fc67e2bBa
000050f134b8B0Db3D9Cc3F6cB262D4d4445Ee28
0000344d315050CA9B0938B6511EC342705a1f9c
0000FbBf26f6437AB8e3280A34743120dcB49E8c
000082bB17A3a81bC48241AA9a568B3b1e18f26B
000067279AcdC3E4769663478be88A57CDD7aE49
0000b9945F899874957B62eF8aE46b0B9e4e3231
0000FbBf26f6437AB8e3280A34743120dcB49E8c
00002A2c9535bd5b071d55bf3b2771B6AEc1460a
00003b1a059Bf7a15ffBBDE1e97Ce92c56faaE5d
000082bB17A3a81bC48241AA9a568B3b1e18f26B
```

### Home Bank Addresses

The testnet has three home banks and each bank has its own address to collect transaction fees. You will see oen of these addresses in every tranaction. 

0000

```
000085f904e427a2721738930681ca7AA2E7984B
```

0001

```
00013e98C16bAAcD74b8EBD24c2911c299520e7a
```
0002

```
0002502F06d625dcc335c3FC7F8B40B8cb3f1c9c
```
