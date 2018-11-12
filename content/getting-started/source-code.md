---
title: "Java Source Code Command Line"
date: 2018-11-11T10:19:10-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---


**Please note that this is for Java developers who are interested in digging into the source code to understand how the taiji blockchain works and planning to contribute to the project. If you are not familiar with Java, please choose [Java standalone command line][] or [Docker command line][] to start.**

Currently, there is only one Java command line client available, and more are coming. Before installing and building from the source code, you need to get your environment ready. As this client is not packaged as executable, so you have to check out the [light-blockchain-4j source code][] from github.com and build it by yourself. It is aiming to Java developers or at least for people with a certain level of computer knowledge. 

### Environment

If you don't have JDK 8 and Git installed, please install them on your computer first before following the rest of the steps. 

To ensure that you have Java 8 installed, issue the following command. 

```
java -version
```

And you should see java version "1.8.0_XXX" in the output.


### Clone

Create a workspace folder under your home directory. 

```
cd ~
mkdir taiji-chain
cd taiji-chain
git clone https://github.com/networknt/light-blockchain-4j.git
```

### Build

```
cd light-blockchain-4j
./gradlew build
```

### Create a wallet

If it is built successfully, go to the root folder to run the command line to create an address and a wallet. Please use a password that you can remember, and this wallet can be used for the mainnet once it is up. 

```
cd light-blockchain-4j
./testnet.sh wallet create
```

You can use the wallet generated with the `testnet.sh` for the mainnet. Just copy the wallet file from `config/testnet` to `config/mainnet` will do the trick. If you want to create a wallet used on the mainnet directly, please use the following command. 

```
cd light-blockchain-4j
./mainnet.sh wallet create
```

It will ask a password that is used to encrypt the wallet private key. You need to repeat the same password twice to ensure that there is no typo. Please remember this password or write it down somewhere so that you can access it later. Without this password, nobody can open the wallet file, and the coins and tokens in your wallet won't be accessible anymore. 

The next step is to choose a [chainId][]. Here is the prompt

```
Please choose your chainId: 
Americas 0000 
Asia,Oceania 0001
Europe,Africa 0002
```

If you are located in North America, South America or Caribbean islands, you should type in `0000` as your chain Id.

If you are located in Asia, Australia or New Zealand, you should type in `0001` as your chain Id.

For Europen and African users, please type in `0002` as your chain Id.  


The next step is to choose a location to save your wallet. Here is the command line prompt. 

```
Please enter a destination directory location [config/testnet]:
```

If you don't know how to [customize the client to load the wallet from a different location][], please use the default location by typing the enter key. It takes a few seconds to generate a wallet depending on the speed of your computer. Once it is done, your address and the location of your wallet will be shown on the console. 

```
Wallet file 0000Ee8048e64BeA435B8d624AECDbaf8206a9b0.json successfully created in: config/testnet
```

You can check the content of your wallet file, and it should be something like this. 

```
{"address":"0000Ee8048e64BeA435B8d624AECDbaf8206a9b0","id":"f54b4ee9-03f0-4ec0-a5ae-bcd1827e8ff8","version":3,"crypto":{"cipher":"aes-128-ctr","ciphertext":"2e55ef0f27877372b1961a672e11e2e127676b062937cefdf11c8d96fc993dce","cipherparams":{"iv":"74ab964440a559a9fa7374cea30efbd8"},"kdf":"scrypt","kdfparams":{"dklen":32,"n":262144,"p":1,"r":8,"salt":"08a519daa3afc3d56efa6be115d4ceeadaccaa28db70437a7b69092578c0ab3f"},"mac":"db3b1dba3470b41de7a6c25823a434164d1f045db1cc356c69eafe64057f5692"}}
```

It contains your address, public key and private key which is encrypted by the password you enter during wallet creation. You shouldn't use this example wallet though for the mainnet as someone can brute force the password, and I didn't use a strong password at all. 


### Taiji Faucet

You address is not on the blockchain yet after you create a new wallet. On testnet, you can populate up to 1000 taiji coins per day from [taiji-faucet][]. For mainnet, you need to buy the coins or mine the coins by working for the community. 

In the faucet interface, click the `Faucet` menu and paste the address to the address field and enter amount 1000. Choose currency `TAIJI` and unit `TAIJI`. Then click the `POPULATE` button. You should receive the following message. 

```
{
  "statusCode": 200,
  "code": "SUC10200",
  "message": "OK",
  "description": "The request is handled successfully",
  "severity": "NA"
}
```

If you try to populate more than once within 24 hours, you will receive the following error. 

```
{
  "statusCode": 400,
  "code": "ERR12291",
  "message": "RATE_LIMIT_REACHED",
  "description": "You can only open the faucet once a day.",
  "severity": "ERROR"
}
```

Now go to the Balance again and click the `BALANCE` button with the same address in the address field. You should see something like this. 

```
{
  "taiji": 100000000000
}
```

The number is based on the smallest [taiji unit][] SHELL in taiji-chain. 

### Send Coins

If you don't know other people's account you can create to addresses to send fund. Or you can simply send fund to our faucet account `0000Ff14aD21d03D20b7eE96d031552cf9dD9072`. 

```
./testnet.sh wallet send
```

You will be asked what currency to transfer. The default is `taiji` and that is the only currency supported at the moment. Please type enter to accept the default. 

Then you will be asked to provide the from address. Copy/paste your address just created and populated with taiji-faucet and hit enter. 

You will be asked to provide the to address. You can use the faucet address above `0000Ff14aD21d03D20b7eE96d031552cf9dD9072` or someone else's address you know. You can create two wallets and use another one for your destination address. Once you copy/paste the destination address, press enter. 

The wallet will be loaded and ask you to provide the password to decrypt the wallet. Enter the password you chosed when creating the wallet. It will indicate that the wallet is loaded succesfully. 

The next step is to choose an amount to transfer. Let's say 10 for the test.

The next step will ask the unit of the currency. Let's use the default taiji.

The last step will give you the summary of the transaction and ask you to type `yes` to confirm the transaction. 

```
Please confirm that you wish to transfer 10 taiji (1000000000 shell) to address 0000Ff14aD21d03D20b7eE96d031552cf9dD9072
```

Type yes and enter to procced. You should see something like this.

```
Funds have been successfully transferred 1000000000 from 0000BaF2A4F804A6De04B633CFF677Bc79258F98 to 0000Ff14aD21d03D20b7eE96d031552cf9dD9072 with status {"statusCode":200,"code":"SUC10200","message":"OK","description":"The request is handled successfully","severity":"NA"}
```

Now you can go to the https://faucet.taiji.io to check the balance changed between these two addresses. 


[light-blockchain-4j source code]: https://github.com/networknt/light-blockchain-4j
[chainId]: /concept/chain-id/
[Docker command line]: /getting-started/docker-command/
[Java standalone command line]: /getting-started/standalone/
[customize the client to load the wallet from a different location]: /tutorial/configuration/
[taiji-faucet]: https://faucet.taiji.io
[taiji unit]: /concept/taiji-unit/
