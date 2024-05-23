
#PROJECT

##OVERVIEN
This is a simple project for a token called "PHILIPPINE PESO with the abbreviation of "PHP". The project defines several public variables to store the details about the token, including the token m abbreviation, and total supply. The project also includes a mapping of addresses to balances, it also includes two functions: BURN and MINT.
##CONTRACT DETAILS

#MAPPING ADRESS
This is a public mapping that associates each address with a balance. The address type is used as the key, and uint is the value type representing the balance of tokens. This mapping allows the contract to keep track of how many tokens each address holds. Since it's public, Solidity automatically generates a getter function to fetch the balance of a given address.

##MINT FUNCTION
 Mint function to increase the total supply and balance of an address function mint

##BURN FUNCTION 
Burn function to decrease the total supply and balance of an address

```solidity


SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.18;

contract MyToken {
    // Public variables to store the details about the coin
    string public tokenName = "PHILIPPINE PESO";
    string public tokenAbbrv = "PHP";
    uint public totalSupply = 0;


    // Mapping of addresses to balances
    mapping(address => uint) public balances;

    // Mint function to increase the total supply and balance of an address
    function mint(address _address, uint _amount) public  {
        totalSupply += _amount;
        balances[_address] += _amount;
    }

    // Burn function to decrease the total supply and balance of an address
    function burn(address _address, uint _amount) public {
        if (balances[_address] >= _amount) {
            totalSupply -= _amount;
            balances[_address] -= _amount;
        }
    }
}

```
