# Noni Token Smart Contract

## Overview
Noni (NOI) is an ERC20-compliant token implemented in Solidity. This smart contract includes functionalities for minting and burning tokens, and it utilizes the `OpenZeppelin` library for secure and standardized implementations.

## Features
- **ERC20 Standard**: Implements the `ERC20` token standard for compatibility with various wallets and exchanges.
- **Minting**: Allows the contract owner to mint new tokens.
- **Burning**: Allows token holders to burn their own tokens.
- **Ownership**: Utilizes OpenZeppelin's `Ownable` contract to manage contract ownership and restrict certain functions to the owner.

## Usage
1. **Deploy the contract**:
   - Use a tool like `Remix`,or `Hardhat` to deploy the contract to a blockchain.
   - Ensure to pass the initial supply as a parameter during deployment.
   - NOTE : I have implemented this code on REMIX IDE

2. **Interacting with the contract**:
   - **Minting Tokens**:
     - Only the owner can mint new tokens.
     - Call the `mint` function with the recipient address and the amount of tokens.
   - **Burning Tokens**:
     - Any token holder can burn their own tokens.
     - Call the `burn` function with the amount of tokens to be burned.

## Functions

### Constructor
```solidity
constructor(uint256 initialSupply) ERC20("Noni", "NOI") Ownable(msg.sender)
```
- Initializes the contract with an initial supply of tokens.
- Mints the initial supply to the contract deployer.

### mint
```solidity
function mint(address to, uint256 amount) public onlyOwner
```
- Mints new tokens to a specified address.
- Can only be called by the owner of the contract.

### burn
```solidity
function burn(uint256 amount) public
```
- Burns a specified amount of tokens from the caller's balance.

## Dependencies
- **OpenZeppelin Contracts**: Provides secure and standardized implementations for ERC20 and ownership functionalities.
  - `@openzeppelin/contracts/token/ERC20/ERC20.sol`
  - `@openzeppelin/contracts/access/Ownable.sol`

## Security
- **Ownership**: Only the contract owner can mint new tokens, preventing unauthorized token creation.
- **Burning**: Token holders can burn their own tokens, reducing the total supply and increasing token scarcity.
