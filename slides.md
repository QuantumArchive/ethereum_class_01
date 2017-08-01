# Introduction

Ethereum

# Smart Contracts?
 > Smart contracts are computer protocols intended to facilitate, 
verify, or enforce the negotiation or performance of a contract. 
Smart contracts were first proposed by Nick Szabo in 1996.[1]

https://en.m.wikipedia.org/wiki/Smart_contract

# Some thoughts

- a call: read data [no cost]
- a transaction: write (change network state) [cost gas]

More transactions = more gas

# A side note 
Metamask, and web3.js


# Example DAPP 
ENS domains.
[http://ens.domains/](http://ens.domains/)


# What are we learning today?
- Basic installations 
- How to create a private Ethereum chain 
- How to setup a dev environment 
- Your first smart contract 
- Bonus content :)

# What tools will we need
- NodeJS
- Geth
- Truffle and Testrpc
- Metamask
- A text editor (atom, sublime, jetbrains)

# Install npm for your system
https://nodejs.org/en/download/current/

# Install geth 
https://www.ethereum.org/cli

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
 simple.sol

# Check Time

# Install truffle and testrpc:
`npm install -g truffle ethereumjs-testrpc`

# Metacoin to the MOON!

`truffle init webpack`

# More Metacoin

From there, you can run `truffle compile`, 
`truffle migrate` and `truffle test` to compile your contracts, 
deploy those contracts to the network, and run their associated unit tests

# Class notes with links
https://github.com/spdz/ethereum_class_01/blob/master/notes.md




