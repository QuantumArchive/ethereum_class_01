# Introduction

Ethereum
![logo](https://www.ethereum.org/images/logos/ETHEREUM-LOGO_LANDSCAPE_Black.png)

# Smart Contracts?
 > Smart contracts are computer protocols intended to facilitate, 
verify, or enforce the negotiation or performance of a contract. 
Smart contracts were first proposed by Nick Szabo in 1996.[1]

https://en.m.wikipedia.org/wiki/Smart_contract

# Some thoughts

a call: read data [no cost]
a transaction: write (change network state) [cost gas]

More transactions = more gas

# A side note 
Metamask, and web3.js
![metamask](https://metamask.io/img/metamask.png)

# Example DAPP 
ENS domains.
[http://ens.domains/](http://ens.domains/)
![ens](http://ens.domains/img/ens.svg)

# What are we learning today?
- Basic installations 
- How to create a private Ethereum chain 
- How to setup a dev environment 
- Your first smart contract 
- Bonus content :)

# What tools will we need
- NodeJS
- Geth
- A text editor (atom, sublime, jetbrains)

# Install npm for your system
https://nodejs.org/en/download/current/

# Install geth 
https://www.ethereum.org/cli

_Note: I use homebrew on a Mac to install npm, geth, and testrpc_

# [BONUS] Install truffle and testrpc:
`npm install -g truffle ethereumjs-testrpc`

At this point you are ready to go.

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

# Metacoin to the MOON!

![To the Moon](https://ethereum.org/images/moon-rocket@2x.png)

`truffle init webpack`

# More Metacoin

From there, you can run `truffle compile`, `truffle migrate` and `truffle test` to compile your contracts, deploy those contracts to the network, and run their associated unit tests

# Resources

https://medium.com/level-k/get-started-with-building-ethereum-dapps-and-smart-contracts-3e726ec9a02f

https://alanbuxton.wordpress.com/2017/07/19/first-steps-with-ethereum-private-networks-and-smart-contracts-on-ubuntu-16-04/

https://www.ethereum.org/token

https://steemit.com/steemit/@belidged/a-guide-on-how-to-ico

About the Swarm
https://swarm-guide.readthedocs.io/en/latest/introduction.html

Whisperin about
https://github.com/ethereum/go-ethereum/wiki/Whisper-Usage
https://github.com/status-im/status-go/blob/b3a56eb00b97d853edcbcb4fb2cf8803fe7a0370/static/tests/whisper.js

Embark
https://github.com/iurimatias/embark-framework

Truffle
http://truffleframework.com/boxes/react

Dapp dev
https://dickolsson.com/building-dapps-on-ethereum-part-1-overview/

https://dapps.ethercasts.com/




