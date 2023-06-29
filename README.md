**#Simple Mint Contract**

This Solidity contract is an implementation of a simple minting mechanism using the ERC721 standard. It allows users to mint tokens by calling the mint function and paying the specified mintPrice. The contract also includes various additional features such as ownership management and the ability to enable/disable minting.

**#License**
This contract is licensed under the Unlicense. You can find the full license text in the SPDX-License-Identifier field at the top of the contract.

**#Prerequisites**
1.Solidity version 0.8.4 or compatible
2.OpenZeppelin Contracts library

**#Contract Details**

#Contract Structure
The SimpleMintContract contract inherits from two other contracts: ERC721 and Ownable. This enables the minting functionality and provides ownership management capabilities.

#State Variables
`mintPrice:` A uint256 variable representing the price in ether for each minted token.
`totalSupply:` A uint256 variable indicating the total number of tokens that have been minted.
`maxSupply:` A uint256 variable specifying the maximum number of tokens that can be minted.
`isMintEnabled:` A bool variable indicating whether minting is currently enabled or disabled.
`mintedWallets:` A mapping that associates each wallet address with the number of tokens it has minted.

#Constructor
The contract's constructor initializes the maxSupply variable to a predetermined value of 10.

#Modifiers
`onlyOwner:` A modifier provided by the Ownable contract, ensuring that only the contract owner can execute certain functions.
#Functions
`toggleIsMintEnabled():` An external function that can be called by the contract owner to toggle the isMintEnabled variable, enabling or disabling minting.
`setMaxSupply(uint256 maxSupply_):` An external function that allows the contract owner to set the maximum supply of tokens.
`mint():` An external payable function that allows users to mint tokens. It performs various checks, such as verifying if minting is enabled, the wallet has not exceeded the maximum allowed tokens, the sent value matches the `mintPrice`, and the `total supply` has not reached the maximum. If all conditions are met, the function mints a new token to the caller's address.

#Usage

1. Deploy the contract to an Ethereum-compatible blockchain network.
2. Set the desired mintPrice and maxSupply values.
3. Call `toggleIsMintEnabled()` to enable or disable minting.
4. Users can call the `mint()` function and send the mintPrice value in ether to mint a token.
5. The mintedWallets mapping keeps track of each wallet's minted tokens.
**Note:** Ensure that you have the necessary ether balance to cover the minting price when calling the mint() function.

Remember to conduct thorough testing and security audits before deploying this contract in a production environment.
