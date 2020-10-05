---
title: "Withdraw Token"
date: 2020-10-05T09:31:59-04:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
reviewed: true
---

Once there is an approval entry in your wallet, you can withdraw tokens up to the approval amount. In the [Create Token](/application/taiji-token/create-token/) section, we have created a TEST1 token with the owner address 0000454FD55b17A041a3F8A1D094FAa2e5DF18Ce. 

To verify the approval entry for the address, query the Token Account and the result: 

```
{
  "TEST1": {
    "approval": {
      "00009c715c281D3A844B2239D42096556E2C210e": 1000000
    }
  }
}

```

To withdraw tokens, fill in the Token Withdraw form. 

![withdraw token](/images/withdraw-token.png)

In the above form, you need to input your owner's wallet address, the password for opening the wallet, the token address or symbol, the approval address and the amount. As the token is newly created, all the tokens are owned by the token address now. So the approval address is the token address in this form. To make the transaction clear, you can also write a comment for the transaction. 


And the result is: 

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
          "data": "AAAAAAJQMDAwMDQ1NEZENTViMTdBMDQxYTNGOEExRDA5NEZBYTJlNURGMThDZQYAClRFU1QxUDAwMDA5YzcxNWMyODFEM0E4NDRCMjIzOUQ0MjA5NjU1NkUyQzIxMGUUigF7ImNvbW1lbnQiOiJXaXRoZHJhdyBmcm9tIHRoZSB0b2tlbiBhZGRyZXNzIHRvIHRoZSBvd25lcidzIGFkZHJlc3MuIn2aoviPn10="
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

Now, let's query the owner's address for the Token Account again. 

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

This time, you can see that the approval value minus 10 to 999990 and the balance is added with amount 10. This means the wallet is holding 10 TEST1 tokens, and the owner can [transfer](/application/taiji-token/transfer-token/) or [approve](/application/taiji-token/approve-token/) up to 10 tokens to other addresses. 

