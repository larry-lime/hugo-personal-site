---
title: "Smart Contract Raffle – DApp Backend"
date: 2022-09-18T01:26:30+08:00
draft: false
author: ["Lawrence Lim"]
ShowToc: true
ShowBreadCrumbs: true
ShowCodeCopyButtons: true
---

## About The Project

My Smart Conract Raffle project is the Solidity smart contract backend of automated and decentralized raffle. The DApp utilizes verifiable random numbers from Chainlink VRFs and uses Chainlink keepers to update or "upkeep" the live contract to maintain the integrity of the raffle. This project was created as a part of Patrick Collin's Solidity and Javascript smart contract course with Free Code Camp.

## Getting Started

### Prerequisites

* [yarn](https://classic.yarnpkg.com/lang/en/docs/install/)

### Installation

1. Clone the repo (backend)
```shell
git clone https://github.com/larry-lime/smart-contract-raffle-backend.git
```
2. Run yarn
```shell
cd smart-contract-raffle-backend && yarn
```

## Usage

####  Deploy to local blockchain
  ```shell
  yarn hardhat deploy
  ```
####  Run tests
  ```shell
  yarn hardhat test
  ```
####  Test Coverage
  ```shell
  yarn hardhat coverage
  ```
####  Interact with live contract

1. Go to the [rinkeby etherscan contract ID](https://rinkeby.etherscan.io/address/0xB2Bf3C63C8aFD537a76fD346Ab88a24B6C76aAf5) 
2. Next, click on "Contract"
3. Then, click on "Read Contract" and then interact with the functions in the form to read state values and data from the contract
4. Finally, click on "Write Contract" and connect web3 to write and interact with the live contract.

