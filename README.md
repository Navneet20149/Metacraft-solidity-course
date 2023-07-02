// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/


contract MyToken {

    // public variables here
    string public tokenName = "Navneet";
    string public abbrv = "Sk";
    uint public totalSupply = 0;
    

    // mapping variable here
    mapping (address=> uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;  

    }


    // burn function
    function burn( address _address,uint _value) public {
        if( balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
        
    }

}

The provided Solidity contract represents a basic token contract with minting and burning functionality. The contract is accompanied by a README file that describes the requirements and functionality of the contract. Let's go through the requirements mentioned in the README file:

Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply):

The contract includes three public variables: tokenName, abbrv, and totalSupply. These variables store the name of the token, its abbreviation, and the total supply of tokens, respectively.
Your contract will have a mapping of addresses to balances (address => uint):

The contract includes a mapping named balances that maps addresses to their token balances. Each address is associated with a uint value representing the balance of tokens held by that address.
You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the "sender" address by that amount:

The contract includes a mint function that takes an address parameter _address and a uint parameter _value. The function increases the totalSupply by the _value and increases the balance of the _address by the same amount. This function allows new tokens to be created and assigned to a specific address.
Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the "sender":

The contract includes a burn function that takes an address parameter _address and a uint parameter _value. The function checks if the balance of the _address is greater than or equal to the _value. If so, it deducts the _value from both the totalSupply and the balance of the _address. This function allows tokens to be destroyed or removed from circulation.
Lastly, your burn function should have conditionals to make sure the balance of the "sender" is greater than or equal to the amount that is supposed to be burned:

The burn function includes a conditional statement that checks if the balance of the _address is greater than or equal to the _value before performing the burning operation. This ensures that the balance of the _address is sufficient to burn the specified amount of tokens.
Overall, this contract provides basic functionality for minting and burning tokens, while keeping track of token balances and the total supply.
