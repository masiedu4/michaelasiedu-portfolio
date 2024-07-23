---
title: Deploying an ERC20 Token for Localhost Testing and Adding to MetaMask
author: Michael Asiedu
pubDatetime: 2024-07-22T13:12:51Z
slug: deploy-erc20-token-on-localhost
featured: false
draft: false
tags:
  - cartesi
  - testnet
  - erc20
description: "Test your ERC20 tokens on localhost"
---

This guide will walk you through the process of deploying an ERC20 token on a local blockchain using Remix IDE and adding it to MetaMask for testing purposes.

## Step 1: Set up Remix IDE

1. Open Remix IDE in your browser at https://remix.ethereum.org/
2. Create a new file named `Token.sol` in the File Explorer

## Step 2: Write the ERC20 Token Contract

Paste the following code into `Token.sol`:

```solidity
pragma solidity ^0.8.0;

import "github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/ERC20.sol";

contract Token is ERC20 {
    constructor(uint256 initialSupply) ERC20("Token", "TOK") {
        _mint(msg.sender, initialSupply);
    }
}
```

## Step 3: Compile the Contract

1. Click on the "Solidity Compiler" tab in the left sidebar
2. Select the appropriate compiler version (0.8.0 or higher)
3. Click "Compile Token.sol"

## Step 4: Deploy the Contract

1. Switch to the "Deploy & Run Transactions" tab
2. Set the environment to "Injected Provider - MetaMask"
3. Ensure MetaMask is connected to your local blockchain
4. Set the initial supply (e.g., 1000000000000000000000 for 1000 tokens with 18 decimals)
5. Click "Deploy" and confirm the transaction in MetaMask

## Step 5: Add the Token to MetaMask

1. Copy the deployed contract address
2. Open MetaMask and click "Import tokens"
3. Paste the contract address into the "Token Contract Address" field
4. The token symbol and decimals should auto-populate
5. Click "Add Custom Token"

Your ERC20 token is now deployed on your local blockchain and added to MetaMask. You can use it for testing purposes, such as transferring tokens between accounts or interacting with other smart contracts.

Remember to reset your local blockchain and redeploy the token when needed, as local blockchains are not persistent.
