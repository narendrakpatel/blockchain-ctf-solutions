# Concept

Before we proceed, one must know a brief overview of how the smart contracts are deployed.

## How the smart contracts are actually deployed?
Smart contracts written in solidity are first compiled into bytecode and then this bytecode is deployed on the ethereum network.

Thus, each contract consists of a EVM bytecode handling the execution and a storage to save the state of the contract. The storage is essentially a key value pair. This storage is public and accesible to all.

After reading the code of the smart contract, we can see that ```uint256 pin``` is initialized in the ```constructor()```. Thus, it must be *calculated* and *stored* in the storage.

Web3 API provides following function to access storage of a contract.

```javascript
web3.eth.getStorageAt(addressHexString, position [, defaultBlock] [, callback])
```

A simple call to a function ```unlocks``` with proper ```_pin``` will result in transfer of 'funds' from contract to our account.
