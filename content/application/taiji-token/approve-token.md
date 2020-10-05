---
title: "Approve Token"
date: 2020-10-05T10:10:36-04:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
reviewed: true
---

The owner can [transfer](/application/taiji-token/transfer-token/) up to the balance amount to another address for the address that is holding any balance for a token. 

Instead of transferring tokens directly to another address, the owner can approve tokens up to the balance amount to another address to allow it to withdraw at any time. 

![approve token](/images/approve-token.png)

This time, the owner's address 0000454FD55b17A041a3F8A1D094FAa2e5DF18Ce approves one TEST1 token to address 0000d0Bb389bDee8EA5F7937fAf2EfB25f0F71b9. 

The response is: 

```
{
  "transaction": {
    "currency": "taiji",
    "d": [
      {
        "0000454FD55b17A041a3F8A1D094FAa2e5DF18Ce": {
          "id": 0,
          "time": 0,
          "toAddress": "000085f904e427a2721738930681ca7AA2E7984B",
          "value": 1000000,
          "data": ""
        }
      }
    ],
    "c": [
      {
        "00009c715c281D3A844B2239D42096556E2C210e": {
          "id": 0,
          "time": 0,
          "toAddress": "00009c715c281D3A844B2239D42096556E2C210e",
          "value": 0,
          "data": "AAAAAANQMDAwMDQ1NEZENTViMTdBMDQxYTNGOEExRDA5NEZBYTJlNURGMThDZQoAClRFU1QxUDAwMDBkMEJiMzg5YkRlZThFQTVGNzkzN2ZBZjJFZkIyNWYwRjcxYjkCkgF7ImNvbW1lbnQiOiJhcHByb3ZlIDEgdG9rZW4gdG8gMDAwMGQwQmIzODliRGVlOEVBNUY3OTM3ZkFmMkVmQjI1ZjBGNzFiOSJ9yO2blJ9d"
        }
      },
      {
        "000085f904e427a2721738930681ca7AA2E7984B": {
          "id": 0,
          "time": 0,
          "toAddress": "000085f904e427a2721738930681ca7AA2E7984B",
          "value": 1000000,
          "data": ""
        }
      }
    ]
  },
  "status": "sent"
}
```

Let's take a look at the owner's address Token Account. 

```
{
  "TEST1": {
    "approval": {
      "00009c715c281D3A844B2239D42096556E2C210e": 999990
    },
    "balance": 9,
    "allowance": {
      "0000d0Bb389bDee8EA5F7937fAf2EfB25f0F71b9": 1
    }
  }
}
```

And the receiver's Token Account

```
{
  "TEST1": {
    "approval": {
      "0000454FD55b17A041a3F8A1D094FAa2e5DF18Ce": 1
    }
  }
}
```

You can see that the owner's address has an entry called allowance with the receiver's address and amount 1. On the receiver side, there is an approval entry with the sender's address and amount 1. 

At this time, the receiver can [withdraw](/application/taiji-token/withdraw-token/) the token to add it to its balance. 
