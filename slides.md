# Introduction

Ethereum

# Smart Contracts?
 > Smart contracts are computer protocols intended to facilitate, 
verify, or enforce the negotiation or performance of a contract. 
Smart contracts were first proposed by Nick Szabo in 1996.[1]

https://en.m.wikipedia.org/wiki/Smart_contract

# Some thoughts

- A call: read data [no cost]
- A transaction: write (change network state) [cost gas]
- More transactions = more gas

# Example DAPP 
ENS domains.
[http://ens.domains/](http://ens.domains/)

# What are we learning today?
- Basic installations 
- How to create a private Ethereum chain 
- How to setup a dev environment 
- A starter smart contract 
- Bonus content :)

# What tools will we need
- NodeJS
- Geth
- A text editor (atom, sublime, jetbrains)
[Bonus Installs]
- Truffle and Testrpc
- Metamask

# A side note
Metamask and Web3.js

# Install npm for your system
[https://nodejs.org/en/download/current/](https://nodejs.org/en/download/current/)

# Install geth 
[https://www.ethereum.org/cli](https://www.ethereum.org/cli)

_Note: I use homebrew on a Mac to install npm, geth, and testrpc_

# Make your own dang chain.

Genesis block JSON file

`{
  "config": {
    "chainId": 1972,
    "homesteadBlock": 0,
    "eip155Block": 0,
    "eip158Block": 0
  },
  "difficulty": "40",
  "gasLimit": "2100000",
  "alloc": {}
}`

# A simple smart contract to forget
Do some math 
`simple.sol`

# Check Time

# Install truffle and testrpc:
Documentation: http://truffleframework.com/docs

`npm install -g truffle ethereumjs-testrpc`

# Metacoin to the MOON!

`truffle init webpack`

# More Metacoin

- Compile code to byte code: `truffle compile`
- Push to blockchain: `truffle migrate`
- Build the Frontend: `npm run build`
- Run Dev Server: `npm run dev`
   
# Class notes with links
https://github.com/spdz/ethereum_class_01/blob/master/notes.md




