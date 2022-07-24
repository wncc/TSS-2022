## WEEK 3 Assignment
#### Problem 1: Based on the ERC721 standard
Now, you've learned enough solidity to write your first contract dealing with NFTs. 
Your task is to use inheritance to write a smart contract based on the ERC721 standard
The links to get the parent contracts and counter functionality are:
* [This](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC721/extensions/ERC721URIStorage.sol) is link top ERC721
* [This](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/access/Ownable.sol) is the link to ownable
* [This](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/Counters.sol) is the link to Counter

You should import these from github by adding a brownie-config.yaml file (do not simply use copy and paste)
The NFT contract should necessarily have the following functions
###### totalSupply()
Returns the total number of NFTs minted to date

###### mintNFT()
Only owner should be able to access it
Increases the total supply by 1
Returns the id of the NFT minted

#### Problem 2: Using Brownie
This problem uses very basics of Python. In case you had trouble with Python during Week 3, you can read [this](https://www.w3schools.com/python/python_functions.asp) article. For this problem you will need to get your week 2 assignment, and deploy and test it.
Create a folder <roll_number> and set up brownie and ganache in it.

Under the subfolders:
###### CONTRACTS
Copy the "BankingSystem" contract, that you made in the last week here.
You can also add additional functions to last week's submission.
Also add problem 1's Smart Contract here.
###### SCRIPTS
Write a script to Deploy the contract to your local ganache blockchain. Use address[0] to be the deployer's address.
###### TEST
Within the same file test.py, write atleast 3 test functions for your banking smart contract.
After each function, add a commment and mention the command which will be used to run only that function for testing.

*Note*: It is optional for you to write the test and deployment scripts for the NFT contract. Compress the entire folder and submit it.





