# **WEEK 2**
_WE'll cover following topics this week:_
> - Events
> - Inheritence
> - ERC20 tokens


# **What is an Event in Solidity?**

To put it simply, events are ways to communicate with a client application or front-end website that something has happened on the blockchain.

The EVM has a logging functionality used to “write” data to a structure outside smart contracts. One such important piece of data is Solidity events. Events allow us to “print” information on the blockchain in a way that is more searchable and gas efficient than just saving to public storage variables in our smart contracts. 

Logs are a special data structure on the blockchain. They cannot be accessed by smart contracts, and give information about what goes on in transactions and blocks. It’s their inaccessibility to smart contracts that makes them cheaper to emit.

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

msg.sender and msg.value are global variables that specify the from address and amount of Ether that was sent. block.timestamp is a way to approximate the current time using the time of the generation of the current block.     

## why use Events?


> - Test your smart contracts for specific variables;
> - Index variables to rebuild storage state;
> - Listen for events to change a front end;
> - Create subgraphs for reading data faster;



</br>

# **Inheritence in Solidity**

Solidity inheritance lets you combine multiple contracts into a single one. The base (or parent) contracts are the ones from which other contracts inherit. Contracts that inherit data are derived (or children).

Inheritance marks several associated contracts with a parent-child relationship. Solidity inheritance rules highly resemble Python, but they have a few differences. Inheritance generates one contract and places it into the blockchain.

These are the cases, explaining when to use inheritance and its advantages:

> - Ability to change one contract and have those modifications reflected in others.
> - Reducement of dependency.
> - Ability to reuse existing code more.


## Using the “is” Keyword in Solidity

To create a derived (or inheriting) contract, simply use the is keyword, as demonstrated in the example code below:

    # A is a derived contract of B
    contract A is B{

    }


As mentioned earlier, Solidity allows for multiple inheritances. You can implement multiple inheritances in solidity as shown in this sample code:

    contract A{

    }

    #single inheritance 
    contract B is A{

    }

    #multiple inheritance 
    contract C is A,B {

    }


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



# **ERC20 Tokens**

_what is ERC20?_

Put simply, the ERC20 standard defines a set of functions to be implemented by all ERC20 tokens so as to allow integration with other contracts, wallets, or marketplaces. This set of functions is rather short and basic.

    function totalSupply() public view returns (uint256);
    function balanceOf(address tokenOwner) public view returns (uint);
    function allowance(address tokenOwner, address spender)
    public view returns (uint);
    function transfer(address to, uint tokens) public returns (bool);
    function approve(address spender, uint tokens)  public returns (bool);
    function transferFrom(address from, address to, uint tokens) public returns (bool);

ERC20 functions allow an external user, say a crypto-wallet app, to find out a user’s balance and transfer funds from one user to another with proper authorization.

The smart contract defines two specifically defined events:

    event Approval(address indexed tokenOwner, address indexed spender,
    uint tokens);
    event Transfer(address indexed from, address indexed to,
    uint tokens);

These events will be invoked or emitted when a user is granted rights to withdraw tokens from an account, and after the tokens are actually transferred.

# **Writing an ERC20 Token in Solidity**

Now that we’ve outlined the basics and explained what it takes to create an ERC20 token, it is time to start writing some logic.

First, we need to define two mapping objects. This is the Solidity notion for an associative or key/value array:

    mapping(address => uint256) balances;
    mapping(address => mapping (address => uint256)) allowed; 

The first mapping object, **balances**, will hold the token balance of each owner account.

The second mapping object, **allowed**, will include all of the accounts approved to withdraw from a given account together with the withdrawal sum allowed for each.

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



    function totalSupply() public view returns (uint256) {
      return totalSupply_;
    }

This function will return the number of all tokens allocated by this contract regardless of owner.

## Get Token Balance of Owner

    function balanceOf(address tokenOwner) public view returns (uint) {
      return balances[tokenOwner];
    }

**balanceOf** will return the current token balance of an account, identified by its owner’s address.

## Transfer Tokens to Another Account

    function transfer(address receiver,
                 uint numTokens) public returns (bool) {
      require(numTokens <= balances[msg.sender]);
      balances[msg.sender] = balances[msg.sender] — numTokens;
      balances[receiver] = balances[receiver] + numTokens;
      emit Transfer(msg.sender, receiver, numTokens);
      return true;
    }


As its name suggests, the transfer function is used to move numTokens amount of tokens from the owner’s balance to that of another user, or receiver. The transferring owner is msg.sender i.e. the one executing the function, which implies that only the owner of the tokens can transfer them to others.

## Approve Delegate to Withdraw Tokens


This function is most often used in a token marketplace scenario.

    function approve(address delegate,
               uint numTokens) public returns (bool) {
      allowed[msg.sender][delegate] = numTokens;
      emit Approval(msg.sender, delegate, numTokens);
      return true;
    }

What **_approve_** does is to allow an owner i.e. **_msg.sender_** to approve a delegate account — possibly the marketplace itself — to withdraw tokens from his account and to transfer them to other accounts.

As you can see, this function is used for scenarios where owners are offering tokens on a marketplace. It allows the marketplace to finalize the transaction without waiting for prior approval.



## Get Number of Tokens Approved for Withdrawal

    function allowance(address owner,
                      address delegate) public view returns (uint) {
      return allowed[owner][delegate];
    }


This function returns the current approved number of tokens by an owner to a specific delegate, as set in the **approve** function.

## Transfer Tokens by Delegate

The **transferFrom** function is the peer of the **approve** function, which we discussed previously. It allows a delegate approved for withdrawal to transfer owner funds to a third-party account.

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


The two **_require_** statements at function start are to verify that the transaction is legitimate, i.e. that the owner has enough tokens to transfer and that the delegate has approval for (at least) **_numTokens_** to withdraw.

In addition to transferring the **_numTokens_** amount from owner to buyer, this function also subtracts **_numTokens_** from the delegate’s allowance. This basically allows a delegate with a given allowance to break it into several separate withdrawals, which is typical marketplace behavior.


