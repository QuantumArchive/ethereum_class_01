# Introduction

What is Ethereum?
- 3 keys
    - Different Blockchain 
    - Featuring Smart Contracts run on the EVM
    - Provides ETH and GAS

# Smart Contracts?
vending machine analogy

- User puts in a coin
- User makes selection
- Vending machine delivers product (renders change if needed)

# Some thoughts

- a call: read data from the ledger [no cost]
- a transaction: write data (change network state) [cost gas]

- More transactions = more gas

# A side note 
Metamask - Awesome browser plugin [light wallet]


web3.js - A way to bridge you app from web 2.0 to web 3.0
https://github.com/ethereum/web3.js/tree/master

# Example DAPP 
ENS domains.
[http://ens.domains/](http://ens.domains/)


# What are we learning today?
- Basic installations 
- how to create a private ethereum chain 
- how to setup a dev environment 
- your first smart contract 

# What tools will we need
- Npm
- Geth
- Mist, the ethereum wallet
- A text editor (atom, sublime, jetbrains)
[Bonus Installs]
- Truffle and Testrpc
- Metamask

# Install npm for your system
https://nodejs.org/en/download/current/

https://changelog.com/posts/install-node-js-with-homebrew-on-os-x

# Install geth
Explain the DL page:
https://ethereum.github.io/go-ethereum/downloads/

Give the docs:
https://www.ethereum.org/cli

_Note: I use homebrew on a Mac to install npm, geth, and solidity_

# Install homebrew on OSX
`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

`brew upgrade`

`brew install node`
`brew tap ethereum/ethereum`
`brew install ethereum`
`brew install solidity`

# Install truffle and testrpc:
`npm install -g truffle ethereumjs-testrpc`

truffle is a framework that makes it easy for you to develop dapps
and post the contracts to the blockchain.
http://truffleframework.com/boxes/react

testrpc is a nifty nodeapp that provides a local dev chain.
https://github.com/ethereumjs/testrpc

At this point you are ready

# Make your own dang chain.

Make a data directory
`mkdir test_chain`

Change to that directory
`cd test_chain/`

Create a new Ethereum account (the coinbase)
`geth --datadir DATADIR/test_chain account new`

0xe172ff89d61aa246d125381d135946fb08b3881b - Primary

 _remember your PASSWORD_

Init our test chain with our custom genesis block info
`geth --datadir DATADIR/test_chain --networkid 1972 init genesis.json`

Fire up geth on the new chain with IPC enabled for mist
`geth --datadir DATADIR/test_chain --networkid 1972 --ipcpath DATADIR/test_chain/geth.ipc console`

ETH Commands to show:
Show your coinbase (the account we created above)
`eth.coinbase`

Start Mining
`miner.start(1)`

Stop mining after a block
`miner.stop()`

Now that we have some ETH, let's send it to another account.

Get the coinbase balance
`eth.getBalance(eth.accounts[0])`

- Create a second account like above
0x590accd4b06f5a7e3ff8080a4f84ee9278dce381 - Secondary

Unlock account to work with it
`personal.unlockAccount(eth.accounts[0])`

Send from on account to another
`eth.sendTransaction({from: eth.accounts[0], to: eth.accounts[1], value: web3.toWei(3,"ether")})`

Mine a block to get the transaction to post
`miner.start(1)`

Check the balance
`eth.getBalance(eth.accounts[1])`

Fun with javascript

function checkAllBalances() {
    var totalBal = 0;
    for (var acctNum in eth.accounts) {
        var acct = eth.accounts[acctNum];
        var acctBal = web3.fromWei(eth.getBalance(acct), "ether");
        totalBal += parseFloat(acctBal);
        console.log("  eth.accounts[" + acctNum + "]: \t" + acct + " \tbalance: " + acctBal + " ether");
    }
    console.log("  Total balance: " + totalBal + " ether");
};
 checkAllBalances();
 

# Check out Mist UI
 /Applications/Ethereum\ Wallet.app/Contents/MacOS/Ethereum\ Wallet --rpc DATADIR/test_chain/geth.ipc

# Connect other nodes

[note: this may not work on the network if firewalls are blocking 30303] 

Get your node info:
`admin.nodeInfo`

On the other nodes add the parameter --bootnodes with the enode: info and the correct IP address 

check for peers
`admin.peers`

# A smart contract to forget
simple.sol

# Install the solidity language [optional]
brew tap ethereum/ethereum
brew install solidity

We can compile the code on our machine, or go to the web
https://ethereum.github.io/browser-solidity/#version=soljson-v0.4.14+commit.c2215d46.js

- Deploy contract
> loadScript("Simple.abi")
true
> loadScript("Simple.bin")

_note: it will ask for coinbase password_

Let's take a look at it in the geth console:
> simple
{
  abi: [{
      constant: false,
      inputs: [{...}, {...}],
      name: "multiply",
      outputs: [{...}],
      payable: false,
      type: "function"
  }, {
      constant: false,
      inputs: [{...}, {...}],
      name: "arithmetics",
      outputs: [{...}, {...}],
      payable: false,
      type: "function"
  }],
  address: undefined,
  transactionHash: "0x75ec2b03f69606262c00a35f8b95412a074c925f2eb06151464be39bac2009ae"
}

If we try to run the function it will not work till we mine a block
> simple.multiply
undefined
> miner.start(1)
> miner.stop()

Now when we run it we can call to the functions

> simple.multiply
function()
> 
> simple.multiply.call(5,6)
30
> simple.arithmetics.call(8,9)
[17, 72]

OK, so that is a simple contract (function) on the blockchain.

---

# Metacoin to the MOON!

Start testrpc 

Build our metacoin truffle box:

`truffle init webpack`

Commands:

  Compile:        `truffle compile`
   - Compile code to byte code
  Migrate:        `truffle migrate`
   - Push to blockchain
  Build Frontend: `npm run build`
   - Build the frontend
  Run Dev Server: `npm run dev`
   - Run the server

Hint: Run the dev server via `npm run dev` to have your changes rebuilt automatically.

Make sure you have an Ethereum client like the ethereumjs-testrpc running on http://localhost:8545.

Documentation: https://github.com/trufflesuite/truffle-init-webpack


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




