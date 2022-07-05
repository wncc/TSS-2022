# Week 1

# Introduction to blockchain

The first thing that clicks in our mind when we hear Blockchain is "Bitcoin"! Of course, they are related to each other but are not the same. Bitcoin is a cryptocurrency, a virtual currency that was the first successful blockchain product. On the contrary, blockchain is a distributed ledger technology that underlies cryptocurrencies like Bitcoin but does not restrict itself to the FinTech industry only. So, let’s first define what blockchain is:

As per the wiki definition, "A Blockchain is the continuously growing list of records, called blocks, which are linked and secured using cryptography. Each block typically contains a hash pointer as a link to a previous block, a timestamp, and transaction data".

The concept of blockchain involves a decentralized consensus via a distributed, permissionless, and trustless protocol.

The reason why the blockchain has gained so much admiration is that:

- It is not owned by a single entity, hence it is decentralized
- The data is cryptographically stored on the blockchain
- It is immutable, so no one can tamper with the data that is inside the blockchain
- The blockchain is transparent, so one can track the data if they want to

## Looking beyond the technical jargon….

A blockchain is made up of two primary components: a decentralized network facilitating and verifying transactions, and the immutable ledger that the network maintains. Everyone in the network can see this shared transaction ledger, but there is no single point of failure from which records or digital assets can be hacked or corrupted. Because of that decentralized trust, there's also no one organization controlling that data, be it a big bank or a tech giant like Facebook or Google. No third parties serve as the gatekeepers of the internet. The power of blockchain's distributed ledger technology has applications across every kind of digital record and transaction. 

 For further understanding, the following can be helpful: [https://www.simplilearn.com/tutorials/blockchain-tutorial](https://www.simplilearn.com/tutorials/blockchain-tutorial)

## History of blockchain

The first blockchain-like protocol was proposed by cryptographer David Chaum in 1982. Later in 1991, Stuart Haber and W. Scott Stornetta wrote about their work on [Consortiums](https://www.anf.es/pdf/Haber_Stornetta.pdf).

But it was Satoshi Nakamoto (presumed pseudonym for a person or group of people) who invented and implemented the first blockchain network after deploying the world’s first digital currency, Bitcoin.

## Designing a blockchain

There are seven major tasks that need to be addressed when designing and
developing a software system that manages ownership by using a purely
distributed peer-to-peer system of ledgers in an open and untrustworthy
environment:

• Describing ownership
• Protecting ownership
• Storing transaction data
• Preparing ledgers to be distributed in an untrustworthy environment
• Distributing the ledgers
• Adding new transactions to the ledgers
• Deciding which ledgers represent the truth

Transactions form the heart of the blockchain problem. Transaction data provide the following information for describing a transfer of ownership:
• An identifier of the account that initiates the transaction and is to transfer ownership to another    account
• An identifier of that account that is to receive ownership
• The amount of the goods to be transferred
• The time the transaction is to be done
• A fee to be paid to the system for executing the transaction
• A proof that the owner of the account who hands-off ownership agrees with that transfer.

The complete history of transaction data is an audit trail that provides evidence of how people acquired and handed off ownership. A transaction is executed by adding it to the history of
transaction data and allowing it to influence the result of aggregating them. The order in which transaction data are added to the history must be preserved in order to yield identical results
when aggregating these data. And this brings us to the next topic on verification of the authenticity of a transaction .

## The authenticity of a user and transaction

The Blockchain must ensure that any transaction announcement reaching a node must be correct and genuine. A few security checks used are:-

### Digital Signature:

All the conventional banking transactions are verified for authenticity using your signature. Similarly, all your transactions in Blockchains are verified using a digital signature. A digital signature is nothing but the result of a Mathematical Function. The mathematical function consists of three important functions.

- A password generator, (sk, pk) = GeneratePassword(size). This password generator generates a secret key and public key when the input size is given. The 'sk' is the secret key and is supposed to be kept secret. The 'pk' is the public key that is made available to everyone in the network. Note that it is impossible to guess the secret key if you have the public key.
- A signature on the document, sign = Signature(sk, msg). The next step involves formation of a signed transaction, which is again a mathematical function whose input is your transaction message and the secret key of the person initializing the transaction. Now, this sign can be safely transmitted and sent to other nodes.
- Finally, a function to verify the authenticity, valid_or_not = verify(pk, msg, sign). A function then verifies the authenticity by comparing the sign, the message and the public key of the person initializing the transaction. The function returns a true or a false depending upon whether the user is authentic or not.

This was how a Digital Signature works in the context of Blockchain. [Here is an article](https://medium.com/faun/what-are-digital-signatures-and-how-do-they-work-195b18c4f42c) that elucidates the concept of digital signatures in general, while [this article](https://medium.com/@xragrawal/digital-signature-from-blockchain-context-cedcd563eee5) talks about them more from the perspective of blockchains.

There are various other algorithms implemented for verifying the signatures of the user, but the idea remains the same. For a more mathematical treatment of the algorithm, refer to the wiki page on Elliptic Curve Digital Signature Algorithm **[Elliptic Curve Digital Signature Algorithm (ECDSA)](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm)**. A short summary of including the crucial steps of ECDSA can be found [here](https://medium.com/coinmonks/ecdsa-the-art-of-cryptographic-signatures-d0bb254c8b96).

Now we look further into the details of the mathematical function acting as the foundations of digital signature.

### Hash Functions:

The **Hash function** is a function. When a program is written, very often, large amounts of data
need to be stored. These are normally stored as [hash table](https://simple.wikipedia.org/wiki/Hash_table). In order to find the data again, some value is calculated. This is like when someone reads a book, and to remember, they put what they read into their own words.

A **[c](https://simple.wikipedia.org/wiki/Cryptography)ryptographic hash function** is a hash function that takes an input (or 'message') and returns a fixed-size string of bytes. The string is called the 'hash value', 'message digest', 'digital fingerprint', 'digest' or 'checksum'.

The ideal hash function has three main properties:

1. It is extremely easy to calculate a hash for any given data.
2. It is extremely unlikely that two slightly different messages will have the same hash.
3. It’s extremely computationally difficult to find the input given the value of the hash function.

The most widely used hashing functions are MD5, SHA1 and SHA-256. Some hashing processes are significantly harder to crack than others. For example, SHA1 is easier to crack than bcrypt.

 Here is a helpful resource to learn more on hashing: [https://medium.com/@rauljordan/the-state-of-hashing-algorithms-the-why-the-how-and-the-future-b21d5c0440de](https://medium.com/@rauljordan/the-state-of-hashing-algorithms-the-why-the-how-and-the-future-b21d5c0440de)

The most popular hashing function in use is the SHA-256(used by bitcoin). To get into its details, have a look at the following:

- [https://www.simplilearn.com/tutorials/cyber-security-tutorial/sha-256-algorithm](https://www.simplilearn.com/tutorials/cyber-security-tutorial/sha-256-algorithm)
- [https://youtu.be/DMtFhACPnTY](https://youtu.be/DMtFhACPnTY)
- [https://youtu.be/S9JGmA5_unY](https://youtu.be/S9JGmA5_unY)

### Hash references:

A cryptographic hash serves as a checksum for a message. If a message has been modified, it will yield a different hash. By associating a hash with a message, we have a basis for managing the integrity of that message: being able to detect if the message gets changed.

One way of associating a hash with a message is with the use of hash pointers. Pointers are used in data structures to allow one data element to refer to another. In processes, a pointer is a memory location. In distributed systems, a pointer may be a name or IP address of a computer and object identifier. A **hash pointer** is a tuple that contains a traditional pointer along with the hash of the data element that is being pointed to. It allows us to validate that the information being pointed to has not been modified.

The same structures that use pointers can be adapted to use hash pointers to create tamper-evident structures. For example, a linked list can be constructed with each element containing a hash pointer to the next element instead of a pointer.

![https://people.cs.rutgers.edu/~pxk/419/notes/images/integrity-blockchain.png](https://people.cs.rutgers.edu/~pxk/419/notes/images/integrity-blockchain.png)

                                                                       Fig: A blockchain

Adding a new block is easy. You allocate the block, copy the *head* hash pointer into it (the `next` pointer), and update the *head* hash pointer to point to the new block and contain a hash of that block.

If an adversary modifies, say, data block 1, we can detect that. The hash pointer in Data-2 will point to Data-1 but the hash of Data-1 will no longer match the hash in the pointer. For a successful attack, the adversary will also need to modify the hash value in the hash pointer in block 2. That will make the hash pointer in block 3 invalid, so that will need to be changed. The adversary will need to change all the hash pointers leading up to the head of the list. If we’re holding on to the head of the list (e.g., in a variable or some trusted storage) so that the adversary cannot modify it, then we will always be able to detect tampering. A linked list using hash pointers is called a **blockchain**.

References(Linked lists): [https://www.geeksforgeeks.org/data-structures/linked-list/](https://www.geeksforgeeks.org/data-structures/linked-list/)

Here is a nice video on the same: [https://youtu.be/IGSB9zoSx70](https://youtu.be/IGSB9zoSx70)

More on cryptographic hash functions: [https://youtu.be/0WiTaBI82Mc](https://youtu.be/0WiTaBI82Mc)

## What’s a block in a blockchain?

Consider a case where A initiates a transaction to B worth 2 BTC (Unit of Bitcoin) and at the same initiates a transaction of the same 2 BTC to his friend C. Both the announcements will travel through different series of nodes and it may happen that at a certain node X, the second announcement reaches first. Now, unaware of the existence of another announcement of the same coin, the node X will add the second announcement and will reject the initial transaction. This would cause an irregularity in the maintained blocks. Thus, time-stamps can not be used as a tool to decide which announcement started first. In other words, a transaction arriving first does not imply it was created first. Hence, a better solution of using Blocks of transactions at once was adopted. This ensures the problem of double spending attack. The blocks can only be added to the chain when the corresponding hash of the block is correctly found. This requires computers to guess the answer. This require huge computation power. Once a correct key is found, the answer is announced to all the nodes and the block is finally added to the chain. On an average, this process takes 10 minutes in Bitcoins. Hence, unlike conventional transaction, it requires more time to complete a transaction and to get added into the chain.

### What it takes to make a chain….

It requires huge computation power and also speed to be able to guess the correct value corresponding to a new block. It is highly unlikely that a single computer will be able to create multiple blocks at a time. It would require huge computation power in order to achieve this. To have a 50% chance of correctly guessing each block, it would require you to have 50% of total computing power of the world. However, in theory, if you are able to make a chain longer than the existing bitcoin chain, then whatever chain you created will be used everywhere and hence, IN THEORY, you can change the entire data of transactions. But this won't happen anytime soon. And this takes us to the next idea of consensus.

## Consensus

A consensus is a dynamic way of reaching agreement in a group. While voting just settles for a majority rule without any thought for the feelings and well-being of the minority, a consensus, on the other hand, makes sure that an agreement is reached which could benefit the entire group as a whole. Following are some of the major Consensus mechanisms that could be implemented in blockchains:

### Proof of Work(PoW):

To summarize how Proof Of Work Protocol works with the blockchain.

- The network has nodes called *miners* who verify transactions and include them in blocks, that get added to the chain
- The miners solve cryptographic puzzles to *mine* a block in order to add to the blockchain
- This process requires immense amount of energy and computational usage
- The puzzles have been designed in a way which makes it hard and taxing on the system
- When a miner solves the puzzle, they present their block to the network for verification
- Verifying whether the block belongs to the chain or not is an extremely simple process
- Miners are incentivized for their resources used in the form of a *Block Reward* associated with each block

**Trivia:** Bitcoin initially started with a block reward of 50 BTC. The block reward is halved after the discovery of every 210,000 blocks, which takes around four years to complete. As of February 2018, one block reward is worth 12.5 BTC.

[This article](https://cointelegraph.com/explained/proof-of-work-explained) helps answer several questions surrounding the concept of Proof of Work.

### Proof of Stake(PoS):

PoW is highly resource intensive and causes scalability issues. A promising alternative is the Proof of Stake mechanism. PoS will make the entire mining process virtual and replace miners with validators.This is how the process will work:

- The validators will have to lock up some of their coins as stake.
- After that, they try to discover a block which they think can be added to the chain by validating it by placing a bet on it.
- If the block gets appended, then the validators will get a reward proportionate to their bets.

Head over to [this article](https://medium.com/nakamo-to/what-is-proof-of-stake-pos-479a04581f3a) in order to understand the processes involved in Proof of Stake consensus. 

The following nicely summarizes the difference and concepts regarding PoW and PoS:

[https://www.geeksforgeeks.org/difference-between-proof-of-work-pow-and-proof-of-stake-pos-in-blockchain/](https://www.geeksforgeeks.org/difference-between-proof-of-work-pow-and-proof-of-stake-pos-in-blockchain/)

### Immutability

In the context of blockchains, it means once data has been written to a blockchain no one can change it. This is implemented by including the hash pointer of a block header in the next block. Tampering with any data on an existing block will change the block hash of that block, resulting in a discrepancy in the next block, all the way to the end of the chain. Since the currently used PoW mechanism is extremely resource-intensive, mining all the blocks again from the tampered block right to the end of the chain is *practically impossible* for the attacker.

## Ethereum:

Ethereum is a decentralized platform created by **Vitalik Buterin** that runs smart contracts: applications that run exactly as programmed without any possibility of downtime, censorship, fraud or third-party interference. In the Ethereum blockchain, instead of mining for bitcoin, miners work to earn **Ether**, a type of crypto token that fuels the network. The second type of token that is used to pay miners fees for including transactions in their block, it is called **gas**. Every smart contract execution requires a certain amount of gas to be sent along with it.

Ethereum’s core innovation, the **Ethereum Virtual Machine (EVM)** is a Turing complete software that runs on the Ethereum network. Instead of having to build an entirely original blockchain for each new application, Ethereum enables the development of potentially thousands of different applications all on one platform.

Several organizations are currently working to scale up Ethereum and fill the loopholes. Some technologies that are areas of active R&D include:

- **Proof Of Stake** (Casper)
- **Plasma:** It is a protocol that will allow the Ethereum blockchain to remove the need to process unnecessary data
- **Sharding:** Network will be divided into smaller parts (*shards*) and individual shard will hold different transaction history
- **Raiden:** The idea centers on taking payment transactions *off-chain*

Check out the following articles to widen your understanding about Ethereum:

- [Beginner's Guide to Understanding Ethereum](https://blockgeeks.com/guides/ethereum/)
- [Detailed Comparison between Ethereum & Bitcoin](https://blockgeeks.com/guides/bitcoin-vs-ethereum-ultimate-comparison-guide/)

The following videos may help in clearer understanding:

- [https://www.simplilearn.com/tutorials/blockchain-tutorial/what-is-ethereum](https://www.simplilearn.com/tutorials/blockchain-tutorial/what-is-ethereum)
- [https://www.simplilearn.com/tutorials/blockchain-tutorial/ethereum-mining](https://www.simplilearn.com/tutorials/blockchain-tutorial/ethereum-mining)

### Ether and gas:

Within Ethereum, there are two native “tokens”, Ether and Gas. But the complex relationship between them often causes some confusion as to their distinction and differing purposes and so this post tries to clear up some of the confusion.

Think of Ether and gas as two different things. Ether is a currency. It *needs* to have intrinsic value as that is the purpose of currency (also *something* needs to have intrinsic value in order to mint as a reward to incentivize people to secure the system). Gas on the other hand is a commodity, like oil. It is essentially a cost of using the system. In this way, it can be thought of as the oil to run your car.

Gas could potentially have no intrinsic monetary value other than allowance to use the system. However, because this isn’t an ideal world where distribution of system operation (whether its through mining or stake) isn’t the same as the system usage (making of transactions), it is necessary for the gas to have intrinsic value as well so those who have gas (from helping operate the system) can trade it to people who need gas (those who use the system) in exchange for something of equivalent intrinsic value. This is the same reason why oil has a price as well.

Now, this is where the difference with oil arises. Ethereum could have implemented Gas as a separate token from Ether (oil is something completely separate from dollars). However, then *every time* you needed to make a transaction and don’t have the gas for it, you’d have to exchange something of value (could be Ether or anything else) for gas. This is massively inefficient. So instead, they implemented Gas as an interface on top of Ether. That way a certain amount of Ether *IS* a unit of gas. With oil, this would be the difference between one barrel of oil costing $50 and one barrel of oil being physically made of $50. Now you can just turn any Ether you have laying around into Gas. It’s essentially an immediate two way peg between Ether and gas.

But the important thing is that these are still two different things. This is why there is a separate Ether market and Gas market. The price of Gas can fluctuate without affecting the price of Ether. The price of Ether can fluctuate without affecting the *real price* of Gas because the Gas/Eth market can react to counteract changes in the Eth/USD market (real value is defined by USD cause it’s the best unit of measure we have).

The value of Ether can still grow based on the increase in adoption of the overall Ethereum system (or speculation of said adoption), even if gas costs went down. As a real world analogy: even though oil refining has become more efficient over time, the explosion of oil use by consumers hasn’t resulted in a decline in the price of a barrel of oil. The real price of oil still grows. Effectively, the growth of the market outpaces the impact of technological gains in efficiency on the price of the oil.

For more on gas, you can refer to the following link and watch the videos: [https://ethereum.org/en/developers/docs/gas/#:~:text=Gas refers to the fee,a transaction on Ethereum successfully.&text=Gas fees are paid in,(10-9 ETH](https://ethereum.org/en/developers/docs/gas/#:~:text=Gas%20refers%20to%20the%20fee,a%20transaction%20on%20Ethereum%20successfully.&text=Gas%20fees%20are%20paid%20in,(10%2D9%20ETH)).

### Bitcoin vs Ethereum:

Bitcoin is the first and most widely used of the cryptocurrencies. Bitcoin launched in January 2009 after the publication of Nakamoto's [white paper](https://www.bitcoin.com/bitcoin.pdf) describing a blockchain currency. It is now a globally traded financial asset with tens of billions of dollars of activity daily.

Bitcoin's network is decentralized, meaning no one controls or owns the Bitcoin network. Instead, the Bitcoin network consists of volunteers -- reportedly 80,000 -- who run open source software on their PCs called nodes. All Bitcoin transactions are recorded on a public ledger known as the blockchain.

Bitcoin has a fixed supply of 21 million coins -- compared to billions for other cryptocurrencies. As of this writing, Bitcoin's value is $48,000.

The reward for finding coins is ownership of them, which can add up for those who find many. While it is possible for someone to put their individual PC to work mining, this is big business and they would be competing with [massive Bitcoin farms](https://www.coininsider.com/biggest-bitcoin-farms/).

Sometimes called "Blockchain 2.0," Ethereum is similar to Bitcoin but adds certain features, including:

- **Conditional transactions.** Transactions can only take place when certain conditions are met. These rules are called "smart contracts." Once the contract is written, it can't be changed. That's why they are called "trustless transactions." If the conditions of the contract aren't met, the currency exchange won't happen.
- **Decentralized applications.** Ethereum has what are called decentralized applications or "dApps." These apps facilitate and enforce smart contracts that run on the distributed Ethereum blockchain network rather than a central server. They are written in a JavaScript-like language called [Solidity](https://www.techtarget.com/whatis/definition/Solidity), which was designed to build dApps.

Like Bitcoin, Ethereum is a distributed network of nodes that verifies transactions and rewards miners with coins. As of this writing, each Ethereum coin is worth approximately $2,800. There is also no limit on the number of coins that can be mined, unlike Bitcoin.

To get into further details, you are encouraged to have a look at the following links:

- [https://www.geeksforgeeks.org/difference-bitcoin-and-ethereum/](https://www.geeksforgeeks.org/difference-bitcoin-and-ethereum/)
- [https://youtu.be/owFY_z5fF-Y](https://youtu.be/owFY_z5fF-Y)
- [https://www.simplilearn.com/tutorials/blockchain-tutorial/ethereum-vs-bitcoin](https://www.simplilearn.com/tutorials/blockchain-tutorial/ethereum-vs-bitcoin)

## Non-Fungible Tokens(NFTs):

In simple terms these are cryptographic assets are based on [blockchain technology](https://www.simplilearn.com/tutorials/blockchain-tutorial/blockchain-technology). They cannot be exchanged or traded equivalently like other cryptographic assets.

Like Bitcoin or Ethereum. The term NFT clearly represents it can neither be replaced nor interchanged because it has unique properties. Physical currency and cryptocurrency are fungible, which means that they can be traded or exchanged for one another.

Key Features of NFT -****

- Digital Asset - NFT is a digital asset that represents Internet collectibles like art, music, and games with an authentic certificate created by blockchain technology that underlies Cryptocurrency.
- Unique - It cannot be forged or otherwise manipulated.
- Exchange - NFT exchanges take place with cryptocurrencies such as Bitcoin on specialist sites.
- The majority of NFTs reside on the Ethereum’s blockchain, a distributed public ledger that records transactions.
- NFTs are individual tokens with valuable information stored in them.
- Because they hold a value primarily set by the market and demand, they can be bought and sold just like other physical types of art.
- NFTs' unique data makes it easy to verify and validate their ownership and the transfer of tokens between owners.

People interested in Crypto-trading and people who like to collect artwork often use NFTs. Other than that, it has some other uses too like:

- Digital Content - The most significant use of NFTs today is in digital content. Content creators see their profits enhanced by NFTs, as they power a creator economy where creators have the ownership of their content over to the platforms they use to publicize it.
- Gaming Items - NFTs have garnered considerable interest from game developers. NFTs can provide a lot of benefits to the players. Normally, in an online game, you can buy items for your character, but that’s as far as it goes. With NFTs, you can recoup your money by selling the items once you’re finished with the
- Investment and Collaterals - Both NFT and DeFi (Decentralized Finance) share the same infrastructure. DeFi applications let you borrow money by using collateral. NFT and DeFi both work together to explore using NFTs as collateral instead.

Have a look at the following videos and blogs to have a more comprehensive idea of NFTs:

- [https://www.blockchainresearchinstitute.org/an-intro-to-blockchain-and-nfts/](https://www.blockchainresearchinstitute.org/an-intro-to-blockchain-and-nfts/)
- [https://www.simplilearn.com/tutorials/blockchain-tutorial/what-is-nft](https://www.simplilearn.com/tutorials/blockchain-tutorial/what-is-nft)

## Some more resources and towards the next module

In the next section of this week’s content, you will be learning the basics of solidity and how to develop smart contracts. Before heading over, you may have a look at the following resources to recapitulate and ensure a firm understanding on the basics of blockchain:

- [https://youtu.be/bBC-nXj3Ng4](https://youtu.be/bBC-nXj3Ng4)
- [https://youtu.be/2yJqjTiwpxM](https://youtu.be/2yJqjTiwpxM)
- Blockchain Basics by Daniel Drescher
- [https://www.ics.uci.edu/~keldefra/teaching/fall2016/uci_compsci134/slides/LEC5-KED.pdf](https://www.ics.uci.edu/~keldefra/teaching/fall2016/uci_compsci134/slides/LEC5-KED.pdf)

# Solidity ( the language of ether )

To write smart contracts we use a programming language called solidity. It is an object-oriented programming language that is quite similar to C++. It is basically a combination of JavaScript, Python, and C++.

Here is a nice article and a short video to give you an introduction to solidity:- 

- [https://moralis.io/solidity-explained-what-is-solidity/](https://moralis.io/solidity-explained-what-is-solidity/)
- [https://youtu.be/kdvVwGrV7ec](https://youtu.be/kdvVwGrV7ec)

## Let’s start with a compiler

To work on solidity we use remix as a compiler. It is an open-source application available online that you don’t even need to download.

[https://remix.ethereum.org](https://remix.ethereum.org/)

Watch this video to get acquainted with the interface:-

[https://youtu.be/WmeWbo7wzGI](https://youtu.be/WmeWbo7wzGI)

## Let’s begin

Read these tutorials to learn in-depth about solidity : 

[https://www.tutorialspoint.com/solidity/index.htm](https://www.tutorialspoint.com/solidity/index.htm) 

The topics which you have to read are:-

- **Basic Syntax**
    
    In this, we talk about pragma which basically tells the compiler which version of solidity we are using. 
    
    ```solidity
    pragma solidity >=0.4.0 <0.6.0;
    pragma solidity ^0.4.0;
    ```
    
    Here both statements are valid the first one is saying we are using versions between 0.4.0 and       0.6.0 while in the second statement all the versions between 0.4.0 and 0.5.0 are valid. 
    
- **First application**
    
    It is a nice example to try.
    
- **Comments**
- **Types**
    
    Here we talk about different data types which are similar to what you have learned in C++.
    
    Here in Solidity, there are special data types :
    
    - `address`: Holds a 20-byte value (size of an Ethereum address).
    - `address payable`: Same as `address`, but with the additional members `transfer` and `send`.
    
    The idea behind this distinction is that `address payable`is an address you can send Ether to while a plain `address`cannot be sent Ether.
    
    Here is another nice blog about data types to which you can refer:-(optional)
    
    [https://blog.logrocket.com/ultimate-guide-data-types-solidity/](https://blog.logrocket.com/ultimate-guide-data-types-solidity/)
    
    Here is a nice video explaining the difference between an address and address payable - 
    
    [https://youtu.be/_Nvl-gz-tRs](https://youtu.be/_Nvl-gz-tRs)
    
- **Variables**
    
    Variables are of three types 
    
    1. Fixed sized: bool, int, etc.
    2. Variable size types
    3. User-defined types
    
    [https://youtu.be/TNZLonjrLYE](https://youtu.be/TNZLonjrLYE)
    
- **Variable Scope**
    
    Private: It can be accessed only within the same contract, not any other contracts.
    
    Internal: `internal`state variables can be accessed from a contract that defined them or any other that inherits from a smart contract. Important to note that smart contract state variables are `internal`by default.
    
    Public: Public state variables can be accessed from any smart contract, including those that hold them or any address. Solidity generates for the `public`state variable a getter function.
    
- **Operators**
- **Loops**
- **Decision making**
- **Strings**
- **Enums**
    
    If you are not familiar with enums in C++ read this:-
    
    [https://www.simplilearn.com/tutorials/cpp-tutorial/cpp-enum](https://www.simplilearn.com/tutorials/cpp-tutorial/cpp-enum)
    
- **Reference Types**
    
    Reference types comprise structs, arrays, and mappings. If you use a reference type, you always have to explicitly provide the data area where the type is stored: `memory`(whose lifetime is limited to a function call), `storage`(the location where the [state variables](https://www.tutorialspoint.com/solidity/solidity_variables.htm#:~:text=State%20Variables%20%E2%88%92%20Variables%20whose%20values,get%20information%20about%20the%20blockchain.) are stored) or `calldata`(special data location that contains the function arguments, only available for external function call parameters).
    
    - Arrays
        
        Dynamic arrays are created by using new keyword.
        
        ```solidity
        uint size = 3;
        uint balance[] = new uint[](size);
        ```
        
        There is another member in array called pop which is used to delete the last element in the array.
        
        We can also use delete keyword to delete an element of an array 
        
        ```solidity
        delete array_name[index]
        ```
        
        Here is a video to learn more about arrays - 
        
        [https://youtu.be/MPBOnChpi0c](https://youtu.be/MPBOnChpi0c)
        
    - Structs
    - Mapping
- **Conversions**
    
    Address payable can be converted to address but the opposite is not true.
    
- **Ether units**
- **Special variables**
    
    Watch this video to get a better understanding of inbuilt variables -
    
    [https://www.youtube.com/embed/XiDs_UmEDG0?end=270](https://www.youtube.com/embed/XiDs_UmEDG0?end=270)
    
- **Style Guide**

Read the whole function part

### **Functions**

The basics syntax of a function is

```solidity
function name of function(<parameter types>) type scope returns(return type){
}
```

Functions are of two types:-

1. Internal - Internal functions can only be called inside the current contract (more specifically, inside the current code unit, which also includes internal library functions and inherited functions) because they cannot be executed outside of the context of the current contract. Calling an internal function is realized by jumping to its entry label, just like when calling a function of the current contract internally. 
2. External - External functions are meant to be used outside the current contract. They cannot be used in the same contract. To use external functions in the same contract use              this.<function name>. External functions consist of an address and a function signature and they can be passed via and returned from external function calls.

By default all functions are internal.

[Scope](https://youtu.be/nep2-1Zzptk) of function:-

- View
    
    • `view` functions can be converted to `non-payable` functions
    
- Pure
    
    • `pure` functions can be converted to `view` and `non-payable` functions
    
- Payable
    
    • `payable` functions can be converted to `non-payable` functions
    

### Solidity common patterns

This part discusses how to give more security to your smart contracts and blockchain network.

Watch the first 3 videos to revise your concepts.

[https://www.dappuniversity.com/articles/solidity-tutorial](https://www.dappuniversity.com/articles/solidity-tutorial)

## Smart contracts

The main difference between Bitcoin and Ethereum is because of smart contracts. 

A smart contract is a self-executing contract with the terms of the agreement between buyer and seller being directly written into lines of code. The code and the agreements contained therein exist across a distributed, decentralized blockchain network. The code controls the execution, and transactions are trackable and irreversible.

It is basically a real-life contract made on a computer. It executes when all the requirements written on it are met. People can transfer money and keep track of work reports through these contracts. These contracts are not made specifically for blockchain but the blockchain network has made it possible to securely transfer smart contracts without any chances of fraud. Solidity is basically a language built to write smart contracts. 

Here are some nice articles and videos about smart contracts. 

[https://www.techtarget.com/searchcio/definition/smart-contract](https://www.techtarget.com/searchcio/definition/smart-contract)

[https://youtu.be/ZE2HxTmxfrI](https://youtu.be/ZE2HxTmxfrI)