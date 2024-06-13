#CREATE-A-TOKEN


##DESCRIPTION

This  solidity program is about implementation or creation of token  on ethereum blockhain.
Here, smart contracts show the fundamentals operation for a token like minting new token ,
burning of existing  token  and tracking the balance of each addresses. The contract will 
store details about the token like name , abbreviation and total supply. BY implementing 
mint function , user can increase the total supply and allocate to specific addresses unlike 
burn function which allows the destruction of the existing token and deducting tokens from a 
designated address.

###EXECUTING PROGRAM

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




/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the address by that amount.
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the address.
    5. Lastly, your burn function should have conditionals to make sure the balance of the account is greater than or equal 
       to the amount that is supposed to be burned.
*/







