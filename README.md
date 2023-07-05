# Flow project3
CryptoPoops: Non-Fungible Token Contract with Borrowing Functionality"

# Description
 The CryptoPoops contract extends the NonFungibleToken contract and introduces NFT functionality by providing the ability to create and manage collections of NFTs, deposit and withdraw NFTs from collections, and borrow NFTs.

# Getting Started
# Installing
Just download the project and move it to the flow playground for the execution


# Executing program
For executing the smart-contract and the scripts, go on to the flow playground website https://play.flow.com/

Importing the NonFungibleToken module: The code imports the NonFungibleToken module from address 0x02. This module likely contains standard functionality for handling non-fungible tokens.

Contract Variables:

totalSupply: A public variable of type UInt64 that represents the total supply of tokens in the contract.
Events:

ContractInitialized: An event that is emitted when the contract is initialized.
Withdraw: An event that is emitted when a token is withdrawn from a collection. It includes the ID of the withdrawn token and the address of the sender.
Deposit: An event that is emitted when a token is deposited into a collection. It includes the ID of the deposited token and the address of the receiver.
Resource Types:

NFT: A resource struct representing a non-fungible token. It implements the NonFungibleToken.INFT interface. It contains fields such as id, name, favouriteFood, and luckyNumber. The init function initializes the id field by assigning it the value of CryptoPoops.totalSupply. It also increments CryptoPoops.totalSupply by 1 and sets the remaining fields with some predefined values.
Resource Interface:

MyCollectionPublic: An interface that defines functions related to managing collections of non-fungible tokens. It includes functions for depositing tokens, getting IDs, and borrowing tokens.
Resource Types:

Collection: A resource struct representing a collection of non-fungible tokens. It implements the NonFungibleToken.Provider, NonFungibleToken.Receiver, NonFungibleToken.CollectionPublic, and MyCollectionPublic interfaces. It contains a dictionary ownedNFTs to store the owned tokens. It provides functions for withdrawing, depositing, getting IDs, and borrowing tokens. The borrowNFT function allows borrowing a non-fungible token by providing the id as input. It returns an immutable reference (&) to the corresponding token of type NonFungibleToken.NFT. It uses the dictionary ownedNFTs to find the token with the given id and returns it as an immutable reference. If the token does not exist, it returns nil. The borrowAuthNFT function is similar but returns an authenticated reference to the token.
Transaction Functions:

createEmptyCollection(): A public function that creates and returns an empty collection of non-fungible tokens.
Resource Minter:

Minter: A resource struct representing a minter. It provides functions for creating new non-fungible tokens (createNFT) and minters (createMinter).
Contract Initialization:

The init() function initializes the contract by setting the totalSupply to 0 and emitting the ContractInitialized event. It also saves a new instance of Minter to the /storage/Minter address.
Overall, this code extends the functionality of the NonFungibleToken contract by introducing a custom token struct, a collection struct, and additional functions for managing non-fungible tokens. It provides the ability to create tokens, minters, and collections, as well as perform operations such as depositing, withdrawing, and borrowing tokens.

# Help
Make sure to watch the tutorials properly with an implementation of the smart contract. Once you understand the concept, you will create an impact.

Authors
ISHIKA ANASANE
