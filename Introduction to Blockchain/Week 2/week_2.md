# **WEEK 2**
_WE'll cover following topics this week:_
> - Events
> - Inheritence
> - Error Handling
> - ERC20 tokens


# **What is an Event in Solidity?**

Events and logs in Ethereum  facilitate communication between smart contracts and their user interfaces. In traditional web development, a server response is provided in a callback to the frontend. In Ethereum, when a transaction is mined, smart contracts can emit events and write logs to the blockchain that the frontend can then process.


**_Let's understand this better with an example:_**

**To declare a new event:**
  Solidity defines events with the event keyword. After events are called, their arguments are placed in the blockchain

    event Deposit(
        address user,
        uint ether_amount,
        uint time
        );

 The definition of the event contains the name of the event and the parameters you want to save when you trigger the event.

 Then you need to emit your event within the function:

    function deposit() public payable{
        /*
           some code..
        */
     emit Deposit(msg.sender, msg.value , block.timestamp);
     }

`` msg.sender `` and ` msg.value` are global variables that specify the from address and amount of Ether that was sent. block.timestamp is a way to approximate the current time using the time of the generation of the current block.     

## why use Events?

Events can be confusing because they can be used in different ways. A There are 3 main use cases for events and logs:

> - Smart contract return values for the user interface
> - Asynchronous triggers with data
> - A cheaper form of storage



</br>

If you feel like watching a video tutorial for events refer [this](https://youtu.be/GcEMOWU-2Hc) video.


# **Inheritence in Solidity**

Solidity inheritance lets you combine multiple contracts into a single one. The base (or parent) contracts are the ones from which other contracts inherit. Contracts that inherit data are derived (or children).

Inheritance marks several associated contracts with a parent-child relationship. Solidity inheritance rules highly resemble Python, but they have a few differences. Inheritance generates one contract and places it into the blockchain.

These are the cases, explaining when to use inheritance and its advantages:

> - Ability to change one contract and have those modifications reflected in others.
> - Reducement of dependency.
> - Ability to reuse existing code more.


## Using the “is” Keyword in Solidity

To create a derived (or inheriting) contract, simply use the `is` keyword, as demonstrated in the example code below:

    # A is a derived contract of B
    contract A is B{

    }


As mentioned earlier, Solidity allows for multiple inheritances. You can implement multiple inheritances in solidity as shown in this sample code:

    ```solidity
    contract A{

    }

    #single inheritance 
    contract B is A{

    }

    #multiple inheritance 
    contract C is A,B {

    }
    ```


Derived contracts access all non-private members (state variables and internal functions as well). It is not possible to access them externally through **this** keyword.


## Arguments for Base Constructors

Solidity calls constructors of the base contracts by following linearization rules. If such constructors have arguments, derived contracts have to indicate all of them. You can achieve this in two ways:

Example:

    pragma solidity >=0.4.22 <0.7.0;

    contract Base {
    uint x;
    constructor(uint _x) public { x = _x; }
    }

You can directly indicate the arguments in the inheritance list:

    contract Derived1 is Base(7) {
    constructor() public {}
    }


You can specify arguments through a modifier of the derived constructor:

    contract Derived2 is Base {
    constructor(uint _y) Base(_y * _y) public {}
    }

> The first way specifies arguments in the inheritance list  **( is Base(7) )**.

> The second way calls a modifier as a part of the constructor argument  
**( Base(_y * _y) )**.


You have to apply only one option for adding arguments. If you use both, it will return an error.

> Tip: choose the first method when the constructor argument is a constant and defines or describes the way contract works. Use the second when the base arguments rely on one of the derived contracts.

In cases when a derived contract does not include arguments for all the Solidity constructors of base contracts, the contract becomes abstract.

> Note: abstract contracts are contracts that do not define their functions fully.


Go through [this](https://medium.com/0xcode/inheritance-in-smart-contracts-using-object-oriented-methodology-ca43fa4775a1) article on inheritence as well!


# **Error Handling**

Errors and exceptions are the norms in programming and Solidity provide ample infrastructure for managing both.

  From version 4.10 of Solidity newer error handling constructs were introduced and therefore the throw
 was made obsolete. These were the assert, require, and revert statements

Read [this](https://www.geeksforgeeks.org/solidity-error-handling/) article and watch [this](https://www.youtube.com/watch?v=1Mi1ub9bIv8&list=PLbbtODcOYIoE0D6fschNU4rqtGFRpk3ea&index=25) video as well



If you confusion over when to use ``Assert()`` and when to use ``require()``
read [this] (https://codedamn.com/news/solidity/assert-vs-require-in-solidity) article.



# **ERC20 Tokens**

_what is ERC20?_

Put simply, the ERC20 standard defines a set of functions to be implemented by all ERC20 tokens so as to allow integration with other contracts, wallets, or marketplaces. This set of functions is rather short and basic.

    ```solidity
    function totalSupply() public view returns (uint256);
    function balanceOf(address tokenOwner) public view returns (uint);
    function allowance(address tokenOwner, address spender)
    public view returns (uint);
    function transfer(address to, uint tokens) public returns (bool);
    function approve(address spender, uint tokens)  public returns (bool);
    function transferFrom(address from, address to, uint tokens) public returns (bool);
    ```

ERC20 functions allow an external user, say a crypto-wallet app, to find out a user’s balance and transfer funds from one user to another with proper authorization.

The smart contract defines two specifically defined events:

    ```solidity
    event Approval(address indexed tokenOwner, address indexed spender,
    uint tokens);
    event Transfer(address indexed from, address indexed to,
    uint tokens);
    ```

These events will be invoked or emitted when a user is granted rights to withdraw tokens from an account, and after the tokens are actually transferred.

# **Writing an ERC20 Token in Solidity**

Now that we’ve outlined the basics and explained what it takes to create an ERC20 token, it is time to start writing some logic.

First, we need to define two mapping objects. This is the Solidity notion for an associative or key/value array:

    mapping(address => uint256) balances;
    mapping(address => mapping (address => uint256)) allowed; 

The first mapping object, `balances`, will hold the token balance of each owner account.

The second mapping object, `allowed`, will include all of the accounts approved to withdraw from a given account together with the withdrawal sum allowed for each.

Now that we have the required data structures in place, we can start to actually write the ERC20 logic into the appropriate functions.

## Setting the Number of ICO Tokens

An initial coin offering (ICO) is the cryptocurrency industry's equivalent of an initial public offering (IPO).

Interested investors can buy into an initial coin offering to receive a new cryptocurrency token issued by the company. This token may have some utility related to the product or service the company is offering or represent a stake in the company or project.

There are number of ways of seeting up number of ICO tokens for the needs of our ECR20 tutorial, we shall use the simplest approach:

   Set the total amount of tokens at contract creation time and initially assign all of them to the “contract owner” i.e. the account that deployed the smart contract:

    uint256 totalSupply_;
    constructor(uint256 total) public {
       totalSupply_ = total;
      balances[msg.sender] = _totalSupply;
    }

## Get Total Token Supply


    ```solidity
    function totalSupply() public view returns (uint256) {
      return totalSupply_;
    }
    ```

This function will return the number of all tokens allocated by this contract regardless of owner.

## Get Token Balance of Owner
    ```solidity
    function balanceOf(address tokenOwner) public view returns (uint) {
      return balances[tokenOwner];
    }
    ```

`` balanceOf `` will return the current token balance of an account, identified by its owner’s address.


> Before moving to next function, let's learn about ``require ``
statements. As we might need them later.

The `` require `` statements declare prerequisites for running the function i.e. it declares the constraints which should be satisfied before executing the code



Coming back to ERC20..

## Transfer Tokens to Another Account
    ```solidity
    function transfer(address receiver,
                 uint numTokens) public returns (bool) {
      require(numTokens <= balances[msg.sender]);
      balances[msg.sender] = balances[msg.sender] — numTokens;
      balances[receiver] = balances[receiver] + numTokens;
      emit Transfer(msg.sender, receiver, numTokens);
      return true;
    }
    ```


As its name suggests, the transfer function is used to move numTokens amount of tokens from the owner’s balance to that of another user, or receiver. The transferring owner is msg.sender i.e. the one executing the function, which implies that only the owner of the tokens can transfer them to others.

## Approve Delegate to Withdraw Tokens


This function is most often used in a token marketplace scenario.
    ```solidity
    function approve(address delegate,
               uint numTokens) public returns (bool) {
      allowed[msg.sender][delegate] = numTokens;
      emit Approval(msg.sender, delegate, numTokens);
      return true;
    }
    ```

What `` approve`` does is to allow an owner i.e. ``msg.sender`` to approve a delegate account — possibly the marketplace itself — to withdraw tokens from his account and to transfer them to other accounts.

As you can see, this function is used for scenarios where owners are offering tokens on a marketplace. It allows the marketplace to finalize the transaction without waiting for prior approval.



## Get Number of Tokens Approved for Withdrawal
    ```solidity
    function allowance(address owner,
                      address delegate) public view returns (uint) {
      return allowed[owner][delegate];
    }
    ```


This function returns the current approved number of tokens by an owner to a specific delegate, as set in the ``approve`` function.

## Transfer Tokens by Delegate

The ``transferFrom`` function is the peer of the ``approve`` function, which we discussed previously. It allows a delegate approved for withdrawal to transfer owner funds to a third-party account.
    ```solidity
    function transferFrom(address owner, address buyer,
                     uint numTokens) public returns (bool) {
      require(numTokens <= balances[owner]);
      require(numTokens <= allowed[owner][msg.sender]);
      balances[owner] = balances[owner] — numTokens;
      allowed[owner][msg.sender] =
            allowed[from][msg.sender] — numTokens;
      balances[buyer] = balances[buyer] + numTokens;
      Transfer(owner, buyer, numTokens);
      return true;
    }
    ```



The two ``require`` statements at function start are to verify that the transaction is legitimate, i.e4. that the owner has enough tokens to transfer and that the delegate has approval for (at least) ``numTokens`` to withdraw.

In addition to transferring the ``numTokens`` amount from owner to buyer, this function also subtracts ``numTokens`` from the delegate’s allowance. This basically allows a delegate with a given allowance to break it into several separate withdrawals, which is typical marketplace behavior.




//



# **Modifiers**

Read this [article](https://medium.com/coinmonks/solidity-tutorial-all-about-modifiers-a86cf81c14cb) about modifers.

</br>


Extensibility is key when it comes to building larger, more complex distributed applications (dapps). Solidity offers two ways to facilitate this in your dapps: `` abstract contracts `` and  `` interfaces ``.

## Abstract Contracts

Contracts are identified as abstract contracts when at least one of their functions lacks an implementation. As a result, they cannot be compiled. They can however be used as base contracts from which other contracts can inherit from.

Here’s an example:
    ```solidity
    pragma solidity ^0.4.24;

    contract Person {
    function gender() public returns (bytes32);
    }

    contract Employee is Person {
    function gender() public returns (bytes32) { return "female"; }
    }
    ```


 Along with improved extensibility, abstract contracts provide better self-documentation, instill patterns , and eliminate code duplication.


 ## Interfaces 

 Interfaces are similar to abstract contracts, but they are limited to what the contract’s ABI can represent. In other words, you could convert an ABI into an interface, or vice versa, and no information would be lost. 

Interfaces are expressed using the interface keyword. Here’s an example:

    pragma solidity ^0.4.24;

    interface token {
    function totalSupply() public view returns (uint256);
    function balanceOf(address who) public view returns (uint256);
    function transfer(address to, uint256 value) public returns (bool);
    }



# **Fallback Function and Receive Ether Function**

A fallback function is a function within a smart contract that is called if no other function in the contract matches the specified function in the call. This can happen if the call has a typo or if it specifies no function at all.


> Solidity knows two different functions for that purpose – `` fallback()`` and ``receive()``.

## receive()

The receive() method is used as a fallback function if Ether are sent to the contract and no calldata are provided (no function is specified). It can take any value. If the receive() function doesn’t exist, the fallback() method is used.
</br>
A contract can have at most one receive() function. The receive() function is declared:
    ```solidity

    receive() external payable{
      // your code here…
    } 
    ```

## fallback()

The fallback() function is used if a smart contract is called and no other function matches (not even the receive() function).

It works, if calldata are included. But it is optionally payable.

The declaration looks like that:
    ```solidity
    fallback() external [payable] {
      // your code here…
    }
    ```

Lets do an example:

Let's add a receive fallback function to the Smart Contract so we can simply send 1 Ether to the Contract without directly interacting with a concrete function.
    ```solidity

    //SPDX-License-Identifier: MIT

    pragma solidity 0.8.3;

    contract FunctionsExample {

    mapping(address => uint) public balanceReceived;

    function receiveMoney() public payable {
      
        balanceReceived[msg.sender] += msg.value;
    }

    function withdrawMoney(address payable _to, uint _amount) public {
        require(_amount <= balanceReceived[msg.sender], "not enough funds.");
        
        balanceReceived[msg.sender] -= _amount;
        _to.transfer(_amount);
    } 

    receive() external payable {
        receiveMoney();
    }
    }
    ```
