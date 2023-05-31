# Batch Minting NFTs

## NFT Contract

The NFT contract is an ERC721-compliant non-fungible token contract with additional functionality for minting and managing NFTs.

### Contract Structure

The contract inherits from the following contracts provided by the OpenZeppelin library:

- `ERC721Enumerable`: Provides implementation for ERC721 token with enumeration capabilities.
- `Ownable`: Provides a basic access control mechanism, allowing the contract owner to perform certain actions.

### Token Details

The contract includes the following details for the token:

- `name`: A string representing the name of the token.
- `symbol`: A string representing the symbol of the token.
- `baseURI`: A string representing the base URI for retrieving the token metadata.
- `baseExtension`: A string representing the extension of the metadata file.
- `cost`: A `uint256` variable indicating the cost in Ether required to mint a token.
- `maxSupply`: A `uint256` variable indicating the maximum supply of tokens.

### Functions

The contract provides the following functions:

- `mint()`: Allows users to mint a new token by paying the specified cost. Minting is limited to the maximum supply.
- `walletOfOwner(address _owner)`: Retrieves an array of token IDs owned by a specific address.
- `tokenURI(uint256 tokenId)`: Retrieves the URI for a specific token, concatenating the base URI, token ID, and extension.
- `setCost(uint256 _newCost)`: Allows the contract owner to set the cost required for minting tokens.
- `setBaseURI(string memory _newBaseURI)`: Allows the contract owner to set the base URI for token metadata.
- `withdraw()`: Allows the contract owner to withdraw the contract's balance.

### Internal and Inherited Functions

The contract overrides and utilizes the following internal and inherited functions:

- `_baseURI()`: Internal function that returns the base URI for token metadata.

### Modifiers

The contract includes the `onlyOwner` modifier, which restricts certain functions to be callable only by the contract owner.

### Libraries

The contract imports various libraries from the OpenZeppelin library, including:

- `Strings`: Provides string manipulation functions.
- `Address`: Provides utility functions for working with addresses.

### License

The contract is licensed under the MIT License. Refer to the SPDX-License-Identifier at the top of the code for more details.


## Technology Stack & Tools

- Solidity (Writing Smart Contract)
- Javascript (React & Testing)
- [Web3](https://web3js.readthedocs.io/en/v1.5.2/) (Blockchain Interaction)
- [Truffle](https://www.trufflesuite.com/docs/truffle/overview) (Development Framework)
- [Ganache](https://www.trufflesuite.com/ganache) (For Local Blockchain)

## Requirements For Initial Setup
- Install [NodeJS](https://nodejs.org/en/), should work with any node version below 16.5.0
- Install [Truffle](https://www.trufflesuite.com/docs/truffle/overview), In your terminal, you can check to see if you have truffle by running `truffle version`. To install truffle run `npm i -g truffle`. Ideal to have truffle version 5.4 to avoid dependency issues.
- Install [Ganache](https://www.trufflesuite.com/ganache).

## Setting Up
### 1. Clone/Download the Repository

### 2. Install Dependencies:
```
$ cd nft_batch_minting
$ npm install 
```

### 3. Start Ganache

### 4. Migrate Smart Contracts
`$ truffle migrate --reset`

### 5. Run Batch Script
`$ node ./scripts/mint.js`
