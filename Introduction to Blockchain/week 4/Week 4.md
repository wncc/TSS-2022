# Week 4

Hello guys you have reached the final destination. In this journey, you learned a lot about smart contracts and how they are a pretty cool feature in the Ethereum network. But one thing which may have come to your mind is how can we really interact with a real blockchain network? This final week you will learn how we can use python to interact with blockchain networks and do some amazing stuff using it.

## What is Web3.py?

Web3.py is a python library using which one can interact with nodes in a blockchain. We can also interact with smart contracts, and blocks and send transactions using this. 

There are a few different aspects to developing blockchain applications with Ethereum:
1. Developing smart contracts - writing programs that run on the blockchain with the Solidity programming language.
2. Developing clients that talk to the blockchain - crafting code that reads and writes data from the blockchain (this includes smart contract interaction).

Web3.py enables you to fulfill the second responsibility: developing clients that interact with The Ethereum Blockchain. And not necessarily "clients" like user-facing applications (web applications for example), but "clients" that transact with the blockchain by reading information from it, writing new transaction data to it, or executing business logic with smart contracts. Since you're writing python this "client" might be a script that scrapes blockchain data or a server process that executes a smart contract function for example. Web3.py is a collection of libraries that enable you to do these kinds of things: create Ethereum transactions, read and write data from smart contracts, create smart contracts, and so much more!

Web3.py talks to The Ethereum Blockchain with [JSON RPC](https://en.wikipedia.org/wiki/Remote_procedure_call), which stands for "Remote Procedure Call" protocol. Ethereum is a peer-to-peer network of nodes that distributes all its data across each node in the network. In other words, each node on the network gets a copy of all the code and the data on the network. Web3.py allows us to make requests to an individual Ethereum node on behalf of the entire network with JSON RPC. This will allow us to read and write data to the network through a single node. It's kind of like making HTTP requests to a JSON API on a web server.

## Prerequisites

We will do all python programming in [Google Colab](https://colab.research.google.com/). It is quite an easy software to use you just need a google account to get started. If you are already familiar with python you can also use text editors like VS code, Anaconda, and Sublime Text. 

This week’s content will need you to have a little knowledge of python. Just a little familiarity with python will help. If you are completely new to python watch this video and read this article :

- [https://www.youtube.com/watch?v=zLRifWZihag](https://www.youtube.com/watch?v=zLRifWZihag) (watch up to conditionals)
- [https://www.tutorialspoint.com/python/python_basic_syntax.htm](https://www.tutorialspoint.com/python/python_basic_syntax.htm) (just read the basic syntax)

## Connecting to a node

In your colab notebook firstly download web3 by:

```python
pip install web3
```

Now import Web3 class 

```python
from web3 import Web3
```

To connect to a blockchain you will need a provider. IPC and HTTP are the most famous providers. We will use HTTP as a provider with a link to a node in the blockchain network.  

[Infura](https://infura.io/) is the best remote node link provider which we will use to connect to the blockchain network.

Watch this video to learn how to do this:-

[https://www.youtube.com/watch?v=17hWNcVZsQM&list=PLw-9a9yL-pt3oKQgq_ZYzkMKAkbr8M67P&index=2](https://www.youtube.com/watch?v=17hWNcVZsQM&list=PLw-9a9yL-pt3oKQgq_ZYzkMKAkbr8M67P&index=2)

<aside>
💡 Note: Store the URL as a string. In python, use can store strings in both single and double quotes.

</aside>

```python
infra_url = 'https://mainnet.infura.io/v3/7b5ef25dcaa341498a8e0101bc867c3f' #my project url store it as a string
w3 = Web3(Web3.HTTPProvider(infra_url) #create a connection to node and we can access node using w3
value = w3.isConnected() #returns a boolean indicating whether we are connected to node or note
print(value) #print the value on screen
```

Okay! now you are connected to the main Ethereum blockchain network. All the Ethereum blockchain commands are inside the w3.eth namespace. 

You can get the latest block number on Ethereum using :

```python
w3.eth.blockNumber
```

To get the account balance of an Ethereum address use:

```python
account = '0x00000000219ab540356cBB839Cbe05303d7705Fa'
balance = w3.eth.getBalance(account)
```

You can access Ethereum addresses from [https://etherscan.io/](https://etherscan.io/)  .

The value which you will get is in Wei to convert it into Ether use

```python
balance_ether = w3.fromWei(balance, "ether")
```

Similarly, you can convert ether to Wei using

```python
w3.toWei(Decimal(balance_ether), "wei")
```

To get the complete information of a block :

```python
w3.eth.get.block('latest') #give info of latest block
w3.eth.get.block(123) #give info of block with block number 123
```

## Reading data from pre-deployed contracts

For this, we need to import another file called JSON.

```python
import json
```

In order to read data from smart contracts with Web3.py, we need two things:

1. A Python representation of the smart contract we want to interact with.
2. A way to call the functions on the smart contract when reading the data.

We can get a Python representation of an Ethereum smart contract with the `web3.eth.Contract()` function. This function expects two arguments: one for the smart contract ABI and one for the smart contract address.

A smart contract ABI stands for "Abstract Binary Interface", and is a JSON array that describes how a specific smart contract works.

Watch this video:- [https://youtu.be/prInJEq6JeI](https://youtu.be/prInJEq6JeI)

We can access the contract using : (Below is an example of Shiba Inu token)

```python
address = '0x95aD61b0a150d79219dCF64E1E6Cc01f0B64C4cE'
abi = json.loads('[{"constant":true,"inputs":[],"name":"name","outputs":[{"name":"","type":"string"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"spender","type":"address"},{"name":"value","type":"uint256"}],"name":"approve","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[],"name":"totalSupply","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"sender","type":"address"},{"name":"recipient","type":"address"},{"name":"amount","type":"uint256"}],"name":"transferFrom","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[],"name":"decimals","outputs":[{"name":"","type":"uint8"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"spender","type":"address"},{"name":"addedValue","type":"uint256"}],"name":"increaseAllowance","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"value","type":"uint256"}],"name":"burn","outputs":[],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"account","type":"address"}],"name":"balanceOf","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":true,"inputs":[],"name":"symbol","outputs":[{"name":"","type":"string"}],"payable":false,"stateMutability":"view","type":"function"},{"constant":false,"inputs":[{"name":"spender","type":"address"},{"name":"subtractedValue","type":"uint256"}],"name":"decreaseAllowance","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":false,"inputs":[{"name":"recipient","type":"address"},{"name":"amount","type":"uint256"}],"name":"transfer","outputs":[{"name":"","type":"bool"}],"payable":false,"stateMutability":"nonpayable","type":"function"},{"constant":true,"inputs":[{"name":"owner","type":"address"},{"name":"spender","type":"address"}],"name":"allowance","outputs":[{"name":"","type":"uint256"}],"payable":false,"stateMutability":"view","type":"function"},{"inputs":[{"name":"name","type":"string"},{"name":"symbol","type":"string"},{"name":"decimals","type":"uint8"},{"name":"totalSupply","type":"uint256"},{"name":"feeReceiver","type":"address"},{"name":"tokenOwnerAddress","type":"address"}],"payable":true,"stateMutability":"payable","type":"constructor"},{"anonymous":false,"inputs":[{"indexed":true,"name":"from","type":"address"},{"indexed":true,"name":"to","type":"address"},{"indexed":false,"name":"value","type":"uint256"}],"name":"Transfer","type":"event"},{"anonymous":false,"inputs":[{"indexed":true,"name":"owner","type":"address"},{"indexed":true,"name":"spender","type":"address"},{"indexed":false,"name":"value","type":"uint256"}],"name":"Approval","type":"event"}]')
contract = w3.eth.contract(address = address, abi= abi)
```

To access the functions in this contract we use call() method. 

```python
contract.functions.totalSupply().call()
```

<aside>
💡 Only public and external functions can be called by this.

</aside>

There are some more pre-defined functions like `name()`, `symbol()`, and `balanceOf()` .

We can also read the balance of a given account. Like I took the richest contract owner’s address:-

0x95aD61b0a150d79219dCF64E1E6Cc01f0B64C4cE

```python
balance = contract.functions.balanceOf('0x95aD61b0a150d79219dCF64E1E6Cc01f0B64C4cE').call()
print(balance)C
```

## Sending transactions

In this, we will use new software called ganache. It is basically a locally hosted blockchain service that you can use to practice. 

Download ganache from here:- [https://trufflesuite.com/ganache/](https://trufflesuite.com/ganache/)

Watch this video to know the interface of ganache:-

 [https://www.youtube.com/watch?v=nUEBAS5r4Og](https://www.youtube.com/watch?v=nUEBAS5r4Og)

You can watch this video to know how to send ether from one account to another :

[https://youtu.be/jA0sL3PM2DE](https://youtu.be/jA0sL3PM2DE)

## Calling your own contracts

Firstly make a smart contract in remix. Example:

```solidity
pragma solidity ^0.5.0;

contract Greeting {
    string public greeting;

    function Greeter() public {
        greeting = 'Hello';
    }

    function setGreeting(string memory _set) public{
        greeting = _set;
    }

    function greet() view public returns (string memory){
        return greeting;
    }
}
```

Compile it and go to the deploy section in remix and set the environment to ganache.

It will ask your endpoint fill it with the one in Ganache. 

Now everything is just same. Connect with your Ethereum node the same way you did in the last part and call functions the same way you did in reading data from contracts part.

To get the abi of your smart contract go to compile section and scroll down you will see the copy option for abi and bytecode.

I have set a default account to make transactions. 

<aside>
💡 Use checkSumAddress to write address of contract.

</aside>

```python
ganache_url = 'http://127.0.0.1:7545'
w3 = Web3(Web3.HTTPProvider(ganache_url)
w3.eth.defaultAccount = web3.eth.accounts[0]

abi = json.loads('[
	{
		"constant": false,
		"inputs": [],
		"name": "Greeter",
		"outputs": [],
		"payable": false,
		"stateMutability": "nonpayable",
		"type": "function"
	},
	{
		"constant": false,
		"inputs": [
			{
				"internalType": "string",
				"name": "_set",
				"type": "string"
			}
		],
		"name": "setGreeting",
		"outputs": [],
		"payable": false,
		"stateMutability": "nonpayable",
		"type": "function"
	},
	{
		"constant": true,
		"inputs": [],
		"name": "greet",
		"outputs": [
			{
				"internalType": "string",
				"name": "",
				"type": "string"
			}
		],
		"payable": false,
		"stateMutability": "view",
		"type": "function"
	},
	{
		"constant": true,
		"inputs": [],
		"name": "greeting",
		"outputs": [
			{
				"internalType": "string",
				"name": "",
				"type": "string"
			}
		],
		"payable": false,
		"stateMutability": "view",/
		"type": "function"
	}
]')

address = w3.toChecksumAddress('') # FILL IN YOUR ACTUAL ADDRESS
contract = w3.eth.contract(address = address, abi =abi)

```

After this, you can easily call all your functions and pass values and so on.

## Deploying the smart contract

There are multiple ways you can deploy smart contracts to The Ethereum Blockchain, and we will learn how to deploy using Web3.py. 

First, we need the smart contract ABI and bytecode, which we can copy from Remix.

We already saw how to copy the abi. Similarly, go to the compile section of the remix IDE, click on Compilation Details, click on Bytecode and copy the object in it.

We'll store them as variables here like this:

```python
bytecode = "608060405234801561001057600080fd5b5061049e806100206000396000f3fe608060405234801561001057600080fd5b506004361061004c5760003560e01c8063777256c414610051578063a41368621461005b578063cfae321714610116578063ef690cc014610199575b600080fd5b61005961021c565b005b6101146004803603602081101561007157600080fd5b810190808035906020019064010000000081111561008e57600080fd5b8201836020820111156100a057600080fd5b803590602001918460018302840111640100000000831117156100c257600080fd5b91908080601f016020809104026020016040519081016040528093929190818152602001838380828437600081840152601f19601f82011690508083019250505050505050919291929050505061026a565b005b61011e610284565b6040518080602001828103825283818151815260200191508051906020019080838360005b8381101561015e578082015181840152602081019050610143565b50505050905090810190601f16801561018b5780820380516001836020036101000a031916815260200191505b509250505060405180910390f35b6101a1610326565b6040518080602001828103825283818151815260200191508051906020019080838360005b838110156101e15780820151818401526020810190506101c6565b50505050905090810190601f16801561020e5780820380516001836020036101000a031916815260200191505b509250505060405180910390f35b6040518060400160405280600581526020017f48656c6c6f000000000000000000000000000000000000000000000000000000815250600090805190602001906102679291906103c4565b50565b80600090805190602001906102809291906103c4565b5050565b606060008054600181600116156101000203166002900480601f01602080910402602001604051908101604052809291908181526020018280546001816001161561010002031660029004801561031c5780601f106102f15761010080835404028352916020019161031c565b820191906000526020600020905b8154815290600101906020018083116102ff57829003601f168201915b5050505050905090565b60008054600181600116156101000203166002900480601f0160208091040260200160405190810160405280929190818152602001828054600181600116156101000203166002900480156103bc5780601f10610391576101008083540402835291602001916103bc565b820191906000526020600020905b81548152906001019060200180831161039f57829003601f168201915b505050505081565b828054600181600116156101000203166002900490600052602060002090601f016020900481019282601f1061040557805160ff1916838001178555610433565b82800160010185558215610433579182015b82811115610432578251825591602001919060010190610417565b5b5090506104409190610444565b5090565b61046691905b8082111561046257600081600090555060010161044a565b5090565b9056fea265627a7a72315820fec0da943df8aada944b2b54fceaad5f6319e3727d922360e7b8b44b4e7a2fca64736f6c63430005110032"
```

Next, we'll set the default account as the sender like this:

```python
web3.eth.defaultAccount = web3.eth.accounts[0]
```

In order to deploy the smart contract, we'll instantiate it in Python like this:

```python
Greeter = web3.eth.contract(abi=abi, bytecode=bytecode)
```

Then, we'll deploy it to the network like this, and wait for the transaction receipt like this:

```python
tx_hash = Greeter.constructor().transact()
tx_receipt = web3.eth.waitForTransactionReceipt(tx_hash)
```

Now we can fetch the smart contract from the blockchain and call its functions. We'll read the default greeting first like this:

```python
#Create the contract instance with the newly-deployed address
contract = web3.eth.contract(
    address=tx_receipt.contractAddress,
    abi=abi,
)

print(tx_receipt.contractAddress)

print('Default contract greeting: {}'.format(
    contract.functions.greet().call()
))
```

Then we can update the greeting like this:

```python
# update the greeting
tx_hash = contract.functions.setGreeting('HELLOOOO!!!!').transact()

# Wait for transaction to be mined...
web3.eth.waitForTransactionReceipt(tx_hash)

# Display the new greeting value
print('Updated contract greeting: {}'.format(
    contract.functions.greet().call()
))
```

Yay! You've just deployed an Ethereum smart contract to the blockchain with Python!

If you want to see the thing live in action before you actually do it, you can watch this video:

[https://www.youtube.com/watch?v=UGcInULTCwU&t=217s&ab_channel=DappUniversity](https://www.youtube.com/watch?v=UGcInULTCwU&t=217s&ab_channel=DappUniversity)

Also you can refer to the following documentation: [https://web3py.readthedocs.io/en/latest/contracts.html](https://web3py.readthedocs.io/en/latest/contracts.html)

# Assignment 3:

For this week’s assignment, your task is to build a NFT smart contract using solidity and then deploy it in you Colab notebook. 

Your smart contract should essentially have the following specifications:

A function **totalSupply()** to return the number of NFTs minted

- A function **owns(claimant, token_id)** to verify ownership
- An external function **transfer(destination, token_id)** to transfer ownership of NFTs. Note that your function should take care of all ownership issues that might arise.

Your next task is to deploy the smart contract in a test Ethereum network in python.

Once the contract is deployed, you have to interact with your NFT in Colab. You have to perform at least the following operation:

- Creating NFT
- Performing transactions on the test Ethereum network
- Calling **totalSupply()** before and after the performed transaction

Note: Your NFT might have other attributes and you are free to interact with them from colab. You might be awarded extra points if your NFT has more attributes than said and if you successfully interact with them.

### Hope you enjoyed this course and came to a basic understanding of what is blockchain and how it has the power to revolutionize the web.

## Enjoy coders!

## Bye!