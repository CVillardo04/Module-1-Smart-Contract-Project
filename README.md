# Module-1-Smart-Contract-Project


SmartContractChester is a simple smart contract written in Solidity that allows for the storage, modification, and validation of a single unsigned integer value (storedData). The contract ensures that the value of storedData is always within a specified range (greater than 0 and less than 2000).

# description 

This contract is designed to ensure that the stored value is always within a safe and expected range, and provides mechanisms to interact with and modify the value while maintaining these constraints.

# Getting Started

### Executing program 

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

