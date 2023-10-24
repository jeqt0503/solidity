# Project Title

Solidity Assessment

## Description

Setting up a smart contract with criteria like Token Name, Abbreviation, and Total Supply is necessary to create tokens on a blockchain. You will require a mint function to create and distribute tokens, and a burn function to destroy them. In order to ensure supply integrity, the burn function incorporates conditionals that examine if the address has enough tokens to burn.

## Getting Started

### Installing

* How/where to download your program
* Any modifications needed to be made to files/folders

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Here is an example code of my token:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
string public tokenName = "JERICHO";
string public tokenAbbrv = "JE";
uint public totalSupply = 0;

    // mapping variable here
mapping(address => uint) public balances;

    // mint function
function mint (address token_address, uint token_value) public{
    totalSupply += token_value;
    balances[token_address] += token_value;
}

    // burn function
function burn (address token_address, uint token_value) public{
    if (balances[token_address] >= token_value){
        totalSupply -= token_value;
        balances[token_address] -= token_value;
        }
    }
}

```
For the compilation of the code, click the "Solidity compiler" tab located in the left-hand sidebar and click the "Compile [file_name.sol]" button. After the code has been compiled. It will be available to deploy the contract by clicking the "Deploy & Run Transactions" tab in the left-hand sidebar. Under deployed contracts, the token name, token abbreviation and current total supply of choice can be seen.

If you want to check the code if its working as it should, copy the default address
then paste it in the under mint and mint an amount of your choice. Click on the transact and check the total supply. Then, copy the address to the balances. 

In order to burn the tokens, try doing the same process. Check the total supply and balances if the amount has been reduced by your choice.

For the last step, check if you cannot burn more than what you have, there should be no changes to the total supply and the balances.

Thank you!


## Authors

Jericho Guansing

202010685@fit.edu.ph
