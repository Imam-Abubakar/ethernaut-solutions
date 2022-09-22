# Dummy Level: Hello Ethernaut

This is the level 0 of [Ethernaut](https://ethernaut.openzeppelin.com/) game.

## Requirements
- Knowledge of [Solidity](https://docs.soliditylang.org/en/v0.8.17/)
- Basic Knowledge of [Web3.js](https://web3js.readthedocs.io/en/v1.8.0/getting-started.html)
- Metamask Wallet [check here](https://metamask.io/)


## Getting started
- Make sure to go over the instructions to understand how the game will be played
- You would be using Rinkeby Test Network so make sure you have some RinkebyETH in your wallet
- The level contract methods are injected into the browser console, so you can call your methods there

## Walkthough

First method to be called in the console:

```javascript
await contract.info()

// Result: 'You will find what you need in info1().'
```
Then...
```javascript
await contract.info1()

// Output: 'Try info2(), but with "hello" as a parameter.'
```

Then...
```javascript
await contract.info2("hello")

// Output: 'The property infoNum holds the number of the next info method to call.'
```

Creating a variable to store `infoNum` value:
```javascript
const infoNum = await contract.infoNum()

// Result: undefined
```

Converting `infoNum` variable to string:
```javascript
infoNum.toString()

// Result: '42'
```

Using `info42` as the next method:
```javascript
await contract.info42()

// Output: 'theMethodName is the name of the next method.'
```

Then...
```javascript
await contract.theMethodName()

// Output: 'The method name is method7123949.'
```

Then...
```javascript
await contract.method7123949()

// Output: 'If you know the password, submit it to authenticate().'
```
Since we don't know the password, checking the contract ABI is our best bet:
```javascript
contract

// Output: { abi: ..., address: ..., ...., password: f () }
```

In our contract ABI, there is a `password` method in the contract so we call it:

```javascript
await contract.password()

// Output: 'ethernaut0`
```

Finally..
```javascript
await contract.authenticate('ethernaut0')
```
and confirm the transaction on metamask. Submit instance.

### Successfully Completed
Well done, You have completed this level!!!
