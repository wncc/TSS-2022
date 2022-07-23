# Intro
Welcome back to the week 3 of Introduction to Block-Chain.
By now, you should have become familiar with solidity, smart contracts, and ERC20 tokens.
ERC token contracts keep track of fungible tokens, that is stuff like voting rights and experience points. However, we might need to keep track of collectibles, property tokens and more in which each of the token is unique, i.e. non-fungible. This is where we'll need to go beyond
ERC20. We will then look at brownie, a python based development and testing framework.

### The contents of week 3 are
* ERC721 standard
* ERC777 tokens
* ERC1155 tokens
* Brownie basics
<br>

### ERC721
The ERC-721 introduces a standard for NFT, in other words, this type of Token is unique and can have different value than another Token from the same Smart Contract, maybe due to its age, rarity or even something else like its visual.

All NFTs have a uint256 variable called tokenId, so for any ERC-721 Contract, the pair contract address, uint256 token Id must be globally unique. That said, a dapp can have a "converter" that uses the token Id as input and outputs an image of something cool, like zombies, weapons, skills or amazing kitties!

It provides functionalities like to transfer tokens from one account to another, to get the current token balance of an account, to get the owner of a specific token and also the total supply of the token available on the network. Besides these it also has some other functionalities like to approve that an amount of token from an account can be moved by a third party account.

These are the essential methods of ERC721 contracts :
* function balanceOf(address _owner) external view returns (uint256);
*   function ownerOf(uint256 _tokenId) external view returns (address);
*    function safeTransferFrom(address _from, address _to, uint256 _tokenId, bytes data) external payable;
*    function safeTransferFrom(address _from, address _to, uint256 _tokenId) external payable;
 *   function transferFrom(address _from, address _to, uint256 _tokenId) external payable;
   * function approve(address _approved, uint256 _tokenId) external payable;
   * function setApprovalForAll(address _operator, bool _approved) external;
   * function getApproved(uint256 _tokenId) external view returns (address);
   * function isApprovedForAll(address _owner, address _operator) external view returns (bool);

The essential events of ERC721 are :
   * event Transfer(address indexed _from, address indexed _to, uint256 indexed _tokenId);
  *  event Approval(address indexed _owner, address indexed _approved, uint256 indexed _tokenId);
  *  event ApprovalForAll(address indexed _owner, address indexed _operator, bool _approved);

To learn more checkout [this article](https://docs.openzeppelin.com/contracts/3.x/erc721) or watch the [Video](https://www.youtube.com/watch?v=c_xwYep-gnQ) 
ERC721 Documentation: https://eips.ethereum.org/EIPS/eip-721

### ERC777
ERC-777 is a fungible token standard improving the existing ERC-20 standard. We recommend to review ERC-20 before reading about ERC777
The improvements are:
#### Hooks
Hooks are a function described in the code of a smart contract. Hooks get called when tokens are 
sent or received through the contract. This allows a smart contract to react to incoming or outgoing 
tokens.Functionality of Hooks is:
1) Hooks allow sending tokens to a contract and notifying the contract in a single transaction, 
unlike ERC-20, which requires a double call (approve/transferFrom) to achieve this.
2) Contracts that have not registered hooks are incompatible with ERC-777. The sending contract will 
abort the transaction when the receiving contract has not registered a hook. This prevents accidental 
transfers to non-ERC-777 smart contracts.
3) Hooks can reject transactions.
	
#### Decimals and Compatibility
The standard also solves the confusion around decimals caused in ERC-20. This clarity improves the developer experience.
ERC-777 contracts are also backward compatible with ERC-20
To learn more about ERC777 check out [this article](https://docs.openzeppelin.com/contracts/3.x/erc777) or watch the [Video](https://www.youtube.com/watch?v=WBlmdePrWOg)
ERC777 Documentation: https://eips.ethereum.org/EIPS/eip-777


### ERC1155
A standard interface for contracts that manage multiple token types. A single deployed contract may include any combination of fungible tokens, non-fungible tokens or other configurations (e.g. semi-fungible tokens).

The idea is simple and seeks to create a smart contract interface that can represent and control any number of  fungible and non-fungible token types. In this way, the ERC-1155 token can do the same functions as an ERC-20 and ERC-721 token, and even both at the same time. And best of all, improving the functionality of both standards, making it more efficient, and correcting obvious implementation errors on the ERC-20 and ERC-721 standards.

The features of ERC-1155
* Batch Transfer: Transfer multiple assets in a single call.
* Batch Balance: Get the balances of multiple assets in a single call.
* Batch Approval: Approve all tokens to an address.
* Hooks: Receive tokens hook.
* NFT Support: If supply is only 1, treat it as NFT.
* Safe Transfer Rules: Set of rules for secure transfer.

#### Batch Transfers
The batch transfer works very similar to regular ERC-20 transfers. Let's look at the regular ERC-20 transferFrom function:
   
    // ERC-20
    function transferFrom(address from, address to, uint256 value)         external returns (bool);
    // ERC-1155
    function safeBatchTransferFrom(
        address _from,
        address _to,
        uint256[] calldata _ids,
    uint256[] calldata _values,
    bytes calldata _data
    ) external;
The only difference in ERC-1155 is that we pass the values as an array and we also pass an array of id's. For example 
given ids=[3, 6, 13] and values=[100, 200, 5], the resulting transfers will be
* Transfer 100 tokens with id 3 from _from to _to.
* Transfer 200 tokens with id 6 from _from to _to.
* Transfer 5 tokens with id 13 from _from to _to.

In ERC-1155 we only have transferFrom, no transfer. To use it like a regular transfer, just set the from address to the address that's calling the function

#### Batch Balance
The respective ERC-20 balanceOf call likewise has its partner function with batch support. As a reminder, this is the ERC-20 version:

    // ERC-20
    function balanceOf(address owner) external view returns      (uint256);

    // ERC-1155
    function balanceOfBatch(
        address[] calldata _owners,
        uint256[] calldata _ids
    ) external view returns (uint256[] memory);

Even simpler for the balance call, we can retrieve multiple balances in a single call. We pass the array of owners, followed by the array of token ids.

#### Batch Approval
    // ERC-1155
    function setApprovalForAll(
	    address _operator,
	    bool _approved
    ) external;

	function isApprovedForAll(
	    address _owner,
	    address _operator
	) external view returns (bool);

The approvals are slightly different than ERC-20. Instead of approving specific amounts, you set an operator to approved or not approved via setApprovalForAll.

Reading the current status can be done via is ApprovedForAll. As you can see, it's an all or nothing. You cannot define how many tokens 
to approve or even which token class.

This is intentionally designed with simplicity in mind. You can only approve everything for one address

#### Receive Hook
	function onERC1155BatchReceived(
	    address _operator,
	    address _from,
	    uint256[] calldata _ids,
	    uint256[] calldata _values,
	    bytes calldata _data
	) external returns(bytes4);
Given the EIP-165 support, ERC-1155 supports receive hooks for smart contracts only. The hook function must return a magic predefined bytes4 value which is given as bytes4(keccak256("onERC1155BatchReceived(address,address,uint256[],uint256[],bytes)"))
When the receiving contract returns this value, it is assumed the contract accepts the transfer and knows how to handle the ERC-1155 tokens. Great, no more stuck tokens in a contract!

Safe Transfer Rule
We've touched on a few safe transfer rules already in the previous explanations. But let's look at the most important of the rules:

* The caller must be approved to spend the tokens for the _from address or the caller must equal _from.
* The transfer call must revert if
_to address is 0.
* length of _ids is not the same as length of _values.
* any of the balance(s) of the holder(s) for token(s) in _ids is lower than the respective amount(s) in _values sent to the recipient.
any other error occurs.

Note: All batch functions including the hook also exist as versions without batch. This is done for gas efficiency, considering transferring
just one asset will likely still be the most commonly used way. We've left them out for simplicity in the explanations, including safe transfer rules. 
The names are identical, just remove the 'Batch'.

To learn more checkout [this article](https://docs.openzeppelin.com/contracts/3.x/erc1155) or watch the [Video](https://www.youtube.com/watch?v=Mnv4rNcTumA)





