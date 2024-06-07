## Example
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract Token {
    string public tokenName;
    string public tokenAbbrv;
    uint public totalSupply;

    mapping(address => uint) public balances;

    constructor(string memory name, string memory abbrv, uint initialSupply) {
        tokenName = name;
        tokenAbbrv = abbrv;
        totalSupply = initialSupply;
    }

    function mint(address add, uint value) public {
        totalSupply += value;
        balances[add] += value;
    }

    function burn(address add, uint value) public {
        if (balances[add] >= value) {
            totalSupply -= value;
            balances[add] -= value;
        }
    }
}

# Token Contract
This Solidity smart contract implements a basic token functionality including minting and burning tokens.
## Overview
- Contract Name: Token
- Solidity Version: ^0.8.18
- License:** MIT License
- SPDX-License-Identifier:** MIT
## Description
This contract provides functionality for a token with the following features:
- Ability to mint new tokens.
- Ability to burn existing tokens.
- Tracks token balances for each address.
## Installation
To deploy this contract on the Ethereum blockchain,we need to  follow these steps:
1. Clone this repository.
2. Compile the contract using a Solidity compiler.
3. Deploy the compiled contract to an Ethereum network of your choice.
### Constructor Parameters
- `name`: The name of the token.
- `abbrv`: The abbreviation or symbol of the token.
- `initialSupply`: The initial supply of the token.
### Functions
1. `mint(address add, uint value)`: Mints new tokens and assigns them to the specified address.
2. `burn(address add, uint value)`: Burns tokens from the specified address if the address has sufficient balance.

To deploy this contract and to know the result, we need to follow the following steps:-
1.  we ned to give user-defined values to tokenName,tokenAbbrv,totalSupply respectively.
2. copy the address from ACCOUNT column
3. Go to the deployed contract section click on it 
4. click on mint function block -> paste that address in address column -> assign the some value  to value block -> click on transact
(to know the value of new tokens through totalSupply)
5. click on totalSupply
6. Follow the step 4 and 5 for burn function. (that eventually helps us to know the value  burned token through totalSupply).



