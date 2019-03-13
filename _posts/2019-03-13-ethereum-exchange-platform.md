---
layout: post
title:  "Ethereum exchange platform"
date:   2019-03-13 13:50:00 +0800
categories: ethererum dapp smart contract
---

> A smart contract is a set of promises, 
> specified in digital form, 
> including protocols within which parties perform on the promises
>
> -- <cite>Nick Szabo (1996)</cite>

[Ethereum] (https://www.ethereum.org/) is a decentralized platform for application. [Solidity] (https://solidity.readthedocs.io/en) is an object-oriented, high-level language for the implementation of smart contracts.

My goal was to create a (sort of) gold bars exchange platform where the transactions will be stored on the Ethereum platform. My prototype has been inspired by this sample published on the Azure Blockchain-Workbench github: [Azure simple marketplace](https://github.com/Azure-Samples/blockchain/tree/master/blockchain-workbench/application-and-smart-contract-samples/simple-marketplace). 

After having checked the solidity code in the platform [Remix](https://remix.ethereum.org). I have created a combined front-end / back-end web application (server-side rendering) to test my smart contract. My prototype is an implementation of this [Next.js](https://nextjs.org/), [Redux](https://redux.js.org) boilerplate published [here](https://github.com/tomsoderlund/nextjs-express-mongoose-crudify-boilerplate) on github.

I still used [MongoDB](https://www.mongodb.com/) to store the list of the smart contract created on the blockchain. The purpose is simply to make my front-end app more responsive. But at the end, I will maybe switch to a full blockchain storage solution. 

My PoC is published on Heroku: [https://gold-bars-exchange.herokuapp.com/](https://gold-bars-exchange.herokuapp.com/).

... I just have this interrogation: Is it better to store each asset in a independant contract ? or should I store all my assets in a single mapping structure of the same contract ?
I still don't have the answer...

