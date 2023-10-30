# TOKEN_PROJECT_META
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName="web";
    string public tokenabbrv="3.O";
    uint public totalSupply=0;

    // mapping variable here
    mapping (address => uint ) public balances;

    // mint function
    function mint (address _Address , uint _Value) public {
        totalSupply += _Value;
        balances[_Address] +=_Value;
    }

    // burn function
    function burn (address _Address , uint _Value) public {
        if (balances[_Address] >= _Value){
            totalSupply -= _Value;
            balances[_Address] -= _Value;
        }
    }

}
