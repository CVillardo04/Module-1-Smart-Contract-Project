# Module-1-Smart-Contract-Project


SmartContractChester is a basic Solidity smart contract that stores, modifies, and validates a single unsigned integer value (storedData). The contract guarantees that the value of storedData is always within a given range (higher than zero and less than 2000).

# description 

This contract is intended to guarantee that the stored value remains within a safe and anticipated range, and it includes means for interacting with and modifying the value while adhering to these limitations.

# Getting Started

### Executing program 

. How to run the program

. Step-by-step bullets


. Open Remix IDE

. Create a New File

. Paste the Smart Contract Code


// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

contract SmartContractChester {
    uint public storedData;

    constructor() {
        storedData = 0;
    }
    function setValueChester(uint ChesterX) public {
        require(ChesterX > 0, "Value must be greater than zero");
        require(ChesterX < 2000, "Value must be less than 2000");
        storedData = ChesterX;
    }
    function checkValueChester() public view {
        assert(storedData > 0); // assert statements do not take a second argument
        assert(storedData < 2000);
    }
    function decrementValueChester(uint ChesterY) public {
        if (ChesterY > storedData) {
            revert("Value to decrement is greater than stored data");
        }
        storedData -= ChesterY;
    }
}

## Author 
Chester Villardo
8215358@ntc.edu.ph

## License  
 This project is licensed under the MIT  License - see the .README.mdfile for details
. Compile the Contract

. Deploy the Contract

. Interact with the Deployed Contract


