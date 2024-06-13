# CREATE-A-TOKEN

The Solidity program focuses on implementing Ethereum blockhain tokens through smart contracts, 
demonstrating fundamental operations like minting, burning, and tracking addresses' balances. 
It allows users to increase total supply and allocate tokens to specific addresses.

## DESCRIPTION

This  solidity program is about implementation or creation of token  on ethereum blockhain.
Here, smart contracts show the fundamentals operation for a token like minting new token ,
burning of existing  token  and tracking the balance of each addresses. The contract will 
store details about the token like name , abbreviation and total supply. BY implementing 
mint function , user can increase the total supply and allocate to specific addresses unlike 
burn function which allows the destruction of the existing token and deducting tokens from a 
designated address.

## Getting Started

### EXECUTING PROGRAM

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:



    // SPDX-License-Identifier: MIT
    pragma solidity ^0.8.18;
    contract MyToken {
    // public variables here
    
    string public tokenName;
    string public tokenAbbrv;
    uint256 public totalSupply;

    // mapping variable here
    mapping(address => uint256) public balances;

    // constructor to initialize the token details
    constructor(string memory _name, string memory _abbrv) {
        tokenName = _name;
        tokenAbbrv = _abbrv;
    }

    // mint function
    function mint(address _reciever, uint256 _value) public {
        totalSupply += _value;
        balances[_reciever] += _value;
    }

    // burn function
    function burn(address _sender, uint256 _value) public {
        require(balances[_sender] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_sender] -= _value;
    }
    }



   ### EXPLAINATION OF CODE

* Your contract  have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
* Your contract  have a mapping of addresses to balances (address => uint)
* You have a mint function that takes two parameters: an address and a value. 
   The function then increases the total supply by that number and increases the balance 
   of the address by that amount.
* Your contract  have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
   It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
   and from the balance of the address.
* Lastly, your burn function should have conditionals to make sure the balance of the account is greater than or equal 
   to the amount that is supposed to be burned.

  ## Help

  If you encounter any issues or have questions, please refer to the Solidity documentation for more information on
  Solidity language features and smart contract development.

  ## Author
  
  Riya kumari @Riyakumari27

  ## License
  


   








