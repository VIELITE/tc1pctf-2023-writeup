For this challenge we simply had to call to call a function to get the flag.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

contract Venue{
    string private flag;
    string private message;

    constructor(string memory initialFlag, string memory initialMessage){
        flag = initialFlag;
        message = initialMessage;
    }

    function enterVenue() public view returns(string memory){
        return flag;
    }

    function goBack() public view returns(string memory){
        return message;
    }
}
```
It could simply be loaded in remix to interacted with but i am cool :p ,I used foundry's `cast` 

`cast call 0xf39Fd6e51aad88F6F4ce6aB8827279cffFb92266 "enterVenue()(string)" --rpc-url <url>"`

Flag was: `TCP1P{d0_3nj0y_th3_p4rty_bu7_4r3_y0u_4_VIP?}`



