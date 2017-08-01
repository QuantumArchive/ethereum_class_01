# Introduction

What is Ethereum?
- 3 keys
    - Different Blockchain 
    - Featuring Smart Contracts run on the EVM
    - Provides ETH and GAS

# Smart Contracts?
vending machine analogy

# Some thoughts

a call: read data from the ledger [no cost]
a transaction: write data (change network state) [cost gas]

More transactions = more gas

# A side note 
Metamask - Awesome browser plugin [light wallet]
![metamask](https://metamask.io/img/metamask.png)

web3.js - A way to bridge you app from web 2.0 to web 3.0

# Example DAPP 
ENS domains.
[http://ens.domains/](http://ens.domains/)
![ens](http://ens.domains/img/ens.svg)

# What are we learning today?
- Basic installations 
- how to create a private ethereum chain 
- how to setup a dev environment 
- your first smart contract 

# What tools will we need
- Npm
- Geth
- Mist, ethereum wallet
- A text editor (atom, sublime, jetbrains)

# Install npm for your system
https://nodejs.org/en/download/current/

# Install truffle and testrpc:
npm install -g truffle ethereumjs-testrpc

At this point you are ready, but we will add more for fun.

# Install geth 
https://www.ethereum.org/cli

_Note: use homebrew on a Mac to install npm, geth, and testrpc_


# Make your own dang chain.

Make a data directory
`mkdir test_chain`

Change to that directory
`cd test_chain/`

Create a new Ethereum account
`geth --datadir DATADIR/test_chain account new`

 _remember your PASSWORD_
 
 0xe172ff89d61aa246d125381d135946fb08b3881b

Init our test chain
`geth --datadir DATADIR/test_chain --networkid 1972 init genesis.json`

Fire up geth on the new chain
`geth --datadir DATADIR/test_chain --networkid 1972 console`

ETH Commands to show:
Show your coinbase (the account we created above)
`eth.coinbase`

Start Mining
`miner.start(1)`

Stop mining after a block
`miner.stop()`

Get the coinbase balance
`eth.getBalance(eth.accounts[0])`

Send from on account to another
`eth.sendTransaction({from: eth.accounts[0], to: eth.accounts[1], value: web3.toWei(3,"ether")})`

Mine a block to get the transaction to post
`miner.start(1)`

Check the balance
`eth.getBalance(eth.accounts[1])`


# All the Truffles

Metacoin!

# Metacoin to the MOON!

`truffle init webpack`

From there, you can run `truffle compile`, `truffle migrate` and `truffle test` to compile your contracts, deploy those contracts to the network, and run their associated unit tests

# Some final thoughts

a call: read data [no cost]
a transaction: write (change network state) [cost gas]

More transactions = more gas

Metamask, and web3.js
Example: ENS domains.

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

https://www.omise.co/go



