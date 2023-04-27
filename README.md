# MyToken

This Solidity program is a basic implementation of a custom token on the Ethereum blockchain. The purpose of this program is to demonstrate the syntax and functionality of Solidity by providing a simple example of how to create a token with minting and burning capabilities.

## Description

### Step By StepDescription
Our program defines a contract called "MyToken" which has the following public variables:

* "tokenName": a string representing name of the token (in our example, "Srusti")(you can give any name)
* "tokenAbbry": a string representing abbreviation of the token (in our example, "MTA")(you can give any abbreviation)
* "totalSuply": a uint representing the total supply of the token (initialized to 0)(uint- since it is positive number)
* The contract also has a mapping variable called "balances" which maps addresses to uints, representing the balance of each address in the token.

Our program defines two functions:

* "mint": a function takes two parameters (address and value) and mints new tokens, increasing total supply and balance of specified address.
* "burn": a function takes two parameters (address and value) and burns tokens, reducing total supply the balance of specified address.
* The "burn" function includes a conditional statement to ensure that balance of specified address is greater than or equal to the amount of tokens that are being burned.

## Getting Started

### Executing program

For run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the code into the file.

```javascript
pragma solidity 0.8.18;
contract MyToken {

    // public variables here
   string public tokenName = "Srusti";
   string public tokenAbbry = "MTA";
   uint public totalSuply = 0;
     
    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSuply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
        totalSuply -= _value;
        balances[_address] -= _value;
        }
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the "mint" and "burn" functions, passing in the appropriate parameters.

## Authors
Srusti H S

