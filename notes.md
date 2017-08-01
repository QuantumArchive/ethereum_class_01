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

https://changelog.com/posts/install-node-js-with-homebrew-on-os-x

# Install geth 
https://www.ethereum.org/cli

_Note: use homebrew on a Mac to install npm, geth, and testrpc_

`brew tap ethereum/ethereum`
`brew install ethereum`

# Install truffle and testrpc:
`npm install -g truffle ethereumjs-testrpc`

truffle is a framework that makes it easy for you to develop dapps
and post the contracts to the blockchain.
http://truffleframework.com/boxes/react

testrpc is a nifty nodeapp that provides a local dev chain.
https://github.com/ethereumjs/testrpc

At this point you are ready, but we will add more for fun.

# Make your own dang chain.

Make a data directory
`mkdir test_chain`

Change to that directory
`cd test_chain/`

Create a new Ethereum account
`geth --datadir DATADIR/test_chain account new`

 _remember your PASSWORD_

Init our test chain
`geth --datadir DATADIR/test_chain --networkid 1972 init genesis.json`

Fire up geth on the new chain with IPC for mist
`geth --datadir DATADIR/test_chain --networkid 1972 --ipcpath/DATADIR/test_chain/geth.ipc console`

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

# Connect other nodes

[note: this may not work on the network if firewalls are blocking 30303] 

Get your node info:
`admin.nodeInfo`

on the other nodes add the parameter --bootnodes with the enode info and the correct IP address 

check for peers
`admin.peers`

# A smart contract to forget
simple.sol

# Install the solidity language
brew tap ethereum/ethereum
brew install solidity

`solc -o . --bin --abi simple.sol`

Once that finishes

ls
Simple.abi  Simple.bin  simple.sol

Need to edit the abi and bin to prep it for uploading to the blockchain

ref github versions

load the ABI
`loadScript("Simple.abi")`

Load the BIN
`loadScript("Simple.bin")`
 
 once loaded we can run the app
 `simple`
 and
 `simple.multiply.call(5,6)`
 
 Hopefully that returns 30
  
 `simple.math.call(5,6)`
 Hopefully that returns 11, and 30
 
 
# [test] Mist to load contract
 /Applications/Ethereum\ Wallet.app/Contents/MacOS/Ethereum\ Wallet --rpc DATADIR/test_chain/geth.ipc


# Metacoin to the MOON!

`truffle init webpack`

From there, you can run `truffle compile`, `truffle migrate` and `truffle test` to compile your contracts, deploy those contracts to the network, and run their associated unit tests


# Resources

https://medium.com/level-k/get-started-with-building-ethereum-dapps-and-smart-contracts-3e726ec9a02f

## Great starter article (where the simple.sol contract came from)
https://alanbuxton.wordpress.com/2017/07/19/first-steps-with-ethereum-private-networks-and-smart-contracts-on-ubuntu-16-04/

## Great Dapp dev article
https://dickolsson.com/building-dapps-on-ethereum-part-1-overview/

https://medium.com/@andresilva/step-by-step-guide-to-deploy-your-first-ethereum-contract-in-a-private-network-4dd9d333f112

## Make your own token
https://www.ethereum.org/token

https://steemit.com/steemit/@belidged/a-guide-on-how-to-ico

## About the Swarm
https://swarm-guide.readthedocs.io/en/latest/introduction.html

## Whisperin about
https://github.com/ethereum/go-ethereum/wiki/Whisper-Usage
https://github.com/status-im/status-go/blob/b3a56eb00b97d853edcbcb4fb2cf8803fe7a0370/static/tests/whisper.js

## Embark
https://github.com/iurimatias/embark-framework

## Truffle
http://truffleframework.com/boxes/react

## Find more Dapps
https://dapps.ethercasts.com/




