---
title: "Web Client Demo"
date: 2018-12-13T18:13:51-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

For most users, the command line based client is very hard to use, so we have developed a web-based client to let users install it on his/her computer and access it from the browser. To make it even easier for users to try it out, we have deployed an instance at https://demo.taiji.io for testnet only. 

For users who are using the demo client, you create the wallet on the cloud and it is protected by your password so nobody can open it unless they know your wallet address and password. This is good enough for testnet but it is not recommended for mainnet. You should have your own client running on your own computer and don't reveal your wallet to anyone even it is encrypted with a password. 

The web-client has the exact functionality of the console client; however, given it provides a GUI interface, it is much easier to use than the command line. 


There are three major functions for the web-client at the moment and more blockchain distributed applications will be added in the future. Also there is a home page that contains some links to get more information about the blockchain, the taiji currency and distributed applications. 


## Wallet

Before doing anything on the Taiji blockchain, you need to have a wallet. Within the wallet, you have a private key and a public key. You sign all your transactions to the blockchain with your private key, and all your transactions will be associated with an address which contains 40 characters and derived from your public key. 

On the demo site, you create a wallet and it is saved on our cloud server. You have a password to protect your wallet so it can only be opened by your password. This is relatively safe for testnet. 

To create a wallet, click the `Create Wallet` menu and fill in the form and click the `Wallet` button. 

You need to use a very strong password so nobody can guess it as your address is public information once you have transactions on the blockchain and your wallet resides on a shared location.  

You also need to select your geolocation from the dropdown so that your address will be generated for one of the [home banks][] available for the testnet. For the testnet, you can choose any location but for the mainnet, you'd better choose your exact location as [interchain transaction][] fee might be higher than the [inner chain transaction][]. 

As we are using one aging server to host the entire cluster, the wallet creation might take up to 3 minutes as it needs to search within a large key space to find one with address started with the home bank or location you selected. Please be patient. 

Once the wallet is created, you will be redirected to another page will all the information about your wallet. Please copy the information or at least your address to somewhere and keep your password as a secret. You will need the address for all the interaction with the blockchain. 


## Taiji Currency

Once you have a wallet and an address, you can start some transactions. The currency section contains all the functionalities related to Taiji currency transactions. 

Before you can do anything, you need to access the [https://faucet.tiaji.io][] to populate up to 1000 taiji currency to your wallet on a daily basis. It is free for the testnet without any conditions and the mainnet will be based on the contribution for the community. For more info on how to use the faucet site, please refer to the [taiji-faucet getting started][].

### Currency Balance

After you populate some taiji coins to your wallet, you can query your balance from the demo site. Click the `Currency Balance` menu and copy/paste your address in the text field and click the `Balance` button. The next page will show your balance for all currencies you are holding. Currently, there is only one currency taiji available. 

### Currency Transaction

You can also check your transactions based on your address and optionally your currency symbol. Click the `Currency Transaction` menu and copy/paste your address and click the `TRANSACTION` button to get all your transactions associated with the address. If there are more currencies held in your wallet, they will be all shown up ordered by timestamp. To choose only one coin, you can select the Currency drop-down. As there is only one currency taiji on the blockchain now, the result is the same for now.

### Send Currency

This is the primary function of the blockchain - to facilitate monetary transactions.  You need another address to send the coins. This [page][] contains all the [significant addresses][] for the testnet, and you can work with them. You can also create another wallet and sending coins between them. 


To access the send currency form, click the `Send Currency` menu. You need to fill in the following fields. 

* Currency

There is only one drop-down value available, and it is taiji. 

* Address

This is your wallet address which contains 40 characters. 

* Password

You wallet password provided during wallet creation. 

* To Address

The target address you want to send currency. The server will only validate the format and checksum of the address, but it cannot prevent you to send fund to an unintended wallet. Please double check the `To Address` before hitting the `SEND` button. 

* Amount

The number of coins you want to send based-on the unit selected below. 

* Unit

Select a [unit][] for the amount you input. 

## Token

The token is the first distributed application implemented on the Taiji blockchain. It is similar to Ethereum ERC 20 token but with a significant low fee to use. Everyone can create his token and use it on different use cases. 

### Create Token

You can create a toke with a valid wallet address with at least balance to pay the transaction fee. You also need to choose a currency to associate your token to.

Click the `Create Token` menu to access the form. 

* Currency

Choose the currency chain your token is associated. Taiji is the only option at the moment. 

* Address

You wallet address. Once the token is created, this address will have the approval to withdraw all the supply from the token address. We call this address as owner address for the token.

* Password

Create a token is a special transaction like sending coins to another address. You need to provide your wallet password in order to sign the transaction with your private key. 

* Token Name

Give a name for the token you want to create. 

* Symbol

The symbol of the token. It is unique in the system and can be used in future transaction instead of token address which is hard to remember. It should be one word and all uppercase just like stock symbol on the market. 

* Total Supply

The total number of tokens available. The max limit is the max value of 64bit integer. 

* Decimals

You can split your token to a smaller unit after the decimal. This number control how many values after the decimal point are supported. The internal total supply is the above total supply multiply decimal number of zeros. 

For example, if you choose total supply to 1 million (1000000) and decimals 2 then the internal total supply is 100 million. This allows the min transaction to be one percent of a token. 


### Withdraw Token

If someone holds some tokens in his/her wallet, he/she can approve another address to withdraw that maximum amount up to the holdings. The approved account will have approval amount and the approval address in the token account. Once you noticed that you have approval in your account for a token, you can withdraw it with this `Withdraw Token` action. 

To access it, click the `Withdraw Token` menu to access the form. 

Fill in the following field and then click the `WITHDRAW` button. 

* Address

You wallet address. 

* Password

The password for your wallet.

* Token Address or Symbol

You can paste the token address or symbol of the token here. 

* From Address

Which address to withdraw the token.

* Amount

The amount of the token to be withdrawn.

### Transfer Token

If you are holding some tokens in your account, you can transfer them to another address. 

To access the form, select the `Transfer Token` menu. 

Fill in the form and click the `TRANSFER` button. 

* Address

You wallet address.

* Password

The password for your wallet.

* Token Address or Symbol

Token address or symbol of the token.

* To Address

The address the fund transfer to.

* Amount

The amount of the token to be transferred.


### Approve Token

When you have some tokens, you can approve other address to withdraw from you up to the amount in your holdings. 

To access the form, select the `Approve Token` menu. 

Fill in the form and click the `APPROVE` button. 

* Address

You wallet address.

* Password

The password for your wallet.

* Token Address or Symbol

Token address or symbol of the token.

* To Address

The address the fund transfer to.

* Amount

The amount of the token to be transferred.


### Token Info

Click the `Token Info` to get all the token's information available or just one token by specify token address or token symbol.

Click the `Token Info` to get all the token's information available or just one token by specifying a token address or a token symbol.

For form has only one field to fill in. If you leave it empty, it will return all the available tokens from the system. 


### Token Account

To query token holdings for a particular address, you can click `Token Account` menu to access the form. Enter an address and optionally a symbol. 

If you don't provide a symbol, it will return all the tokens' holdings. If you provide a symbol, only the holdings for that symbol will be returned. 


### Token Transaction

To query token transactions, you can click `Token Transaction` menu to access the form. Enter an address and optionally a symbol. 

If you don't provide a symbol, it will return all the tokens' transactions. If you provide a symbol, only the transactions for that symbol will be returned. 


[home banks]: /concept/home-bank/
[interchain transaction]: /concept/inter-tx/
[inner chain transaction]: /concept/inner-tx/
[https://faucet.tiaji.io]: https://faucet.tiaji.io
[taiji-faucet getting started]: /getting-started/taiji-faucet/
[page]: /getting-started/significant-addresses/
[significant addresses]: /getting-started/significant-addresses/
[unit]: /concept/taiji-unit/
