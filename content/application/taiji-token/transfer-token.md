---
title: "Transfer Token"
date: 2020-10-05T10:10:29-04:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
reviewed: true
---

In the [withdraw-token](/application/taiji-token/withdraw-token/) section, the owner's address 0000454FD55b17A041a3F8A1D094FAa2e5DF18Ce has withdrawn 10 tokens from the approval amount. From the Token Account query result, we can see the balance of 10 tokens. 

```
{
  "TEST1": {
    "approval": {
      "00009c715c281D3A844B2239D42096556E2C210e": 999990
    },
    "balance": 10
  }
}
```

Now, the owner can transfer up to 10 tokens to other addresses. Here is the Transfer Form.


![transfer token](/images/transfer-token.png)

Here is the response of the transfer token. 

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
          "data": "AAAAAARQMDAwMDQ1NEZENTViMTdBMDQxYTNGOEExRDA5NEZBYTJlNURGMThDZQgAClRFU1QxUDAwMDAzMEEyQjU4NUY0ODFCRUI3NjUzNmZiMkU5RTliNGFENjllNjUCoAF7ImNvbW1lbnQiOiJUcmFuc2ZlciAxIFRFU1QxIHRva2VuIHRvIDAwMDAzMEEyQjU4NUY0ODFCRUI3NjUzNmZiMkU5RTliNGFENjllNjUifbL825KfXQ=="
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

After the token transfer, let's take a look at the token account for the owner and the third party. 


The owner address 0000454FD55b17A041a3F8A1D094FAa2e5DF18Ce

```
{
  "TEST1": {
    "approval": {
      "00009c715c281D3A844B2239D42096556E2C210e": 999990
    },
    "balance": 9
  }
}
```

The receiver address 000030A2B585F481BEB76536fb2E9E9b4aD69e65

```
{
  "LIGHT": {
    "approval": {
      "000034113799e761BF51ED17d8D971CA627f1A75": 99999900
    },
    "balance": 100
  },
  "TEST1": {
    "balance": 1
  }
}
```

You can see the send's balance dropped to 9, and the receiver's balance for TEST1 is 1. Also, the receiver is holding another token with the symbol LIGHT.


