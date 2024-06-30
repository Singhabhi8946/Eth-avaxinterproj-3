# Eth-avaxinterproj-3

## My ERC token

## Overview
- This project demonstrates the implementation of an ERC20 token named Myfirstnewtoken using Solidity. The smart contract includes minting functionalities, where only the contract owner can mint new tokens. 
- This project helps developers understand how to create and manage ERC20 tokens while implementing ownership and basic token operations.

## Features
- mint(address to, uint256 amount): Mints new tokens to a specified address. This function can only be called by the contract owner.
- Mints an initial supply of tokens to the contract deployer's address upon deployment.

# Program And Usage

```
// SPDX-License-Identifier: MIT

pragma solidity ^0.8.26;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract Myfirstnewtoken is ERC20, Ownable {
    constructor(address initialOwner)
        ERC20("Myfirstnewtoken", "MFT")
        Ownable(initialOwner)
    {}

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }
}

```

## Testing
1. Open Remix IDE:
Navigate to Remix IDE.

2. Create a New File:
In the "contracts" folder, create a new file named MyToken.sol and paste the Solidity code for the smart contract into the new file.
3. Compile the Contract:

- Click on the "Solidity Compiler" tab in the left panel.
- Ensure the compiler version is set to 0.8.0 or higher.
- Click on the "Compile MyToken.sol" button.
  
4. Deploy the Contract:
- Go to the "Deploy & Run Transactions" tab.
- Select "Injected Web3" in the "Environment" dropdown to use MetaMask for deployment.
- Enter the initial supply of tokens in the constructor arguments field (e.g., 1000000 for 1,000,000 tokens).
- Ensure MyToken is selected in the "Contract" dropdown.
- Click on the "Deploy" button and confirm the transaction in MetaMask.

- mint(address to, uint256 amount): Call this function with the recipient address and the amount of tokens to mint. Only the contract owner can execute this function.
- burn(uint256 amount): Call this function with the amount of tokens to burn from the caller's balance.
- Transfer Tokens: Use the standard ERC20 transfer function to send tokens to another address.
- Check Balance: Use the standard ERC20 balanceOf function to check the token balance of an address.

  ## Author

  Abhinav Singh

  ## Licence

  This project is licensed under the MIT License.



