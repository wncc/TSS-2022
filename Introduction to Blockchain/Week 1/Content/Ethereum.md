# Ethereum

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