This challenge was quite unique, a quiz on storage slot's in solidity. we are given a nc address to interact with and it imediately prompts us the first question in a random order. There where 11 different questions , we are to find the storage slot where `password` is stored. To automate this challenges a bit i made a contract on remix with each chall and assigned correct values to it's variables. And for each of the contracts i made a function

```solidity
 function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }
```

full detailed solution (TL;DR)

```solidity
/ SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;



contract StorageChallenge10 {
    bool private string_true;
    bool private number_false;
    bool private user_true;
    bytes32 private username;
    bytes32 private password;
    bool public status_creds;

    constructor(bool _string,bool _number,bool _user,bytes32 _username,bytes32 _passwd){
        string_true = _string;
        number_false = _number;
        user_true = _user;
        username = _username;
        password = _passwd;
    }

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }

    //slot = 2




}



contract StorageChallenge2 {
    address[2] private investor ;
    uint64 private password = 45;
    bytes32 private user = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address private owner = 0x01CAe69eC24493327A08FaAE459f5251f83d8847;

    constructor(address investor1, address investor2) {
        investor[0] = investor1;
        investor[1] = investor2;
    }

     function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }

    //password storage slot = 2

}


contract StorageChallenge5 {
    address[2] private investor;
    bytes32 private user = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address private owner = 0x01CAe69eC24493327A08FaAE459f5251f83d8847;
    uint64 private password = 65;

    constructor(address investor1, address investor2) {
        investor[0] = investor1;
        investor[1] = investor2;
    }

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }

}

contract StorageChallenge7 {
    bytes32 private key = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    bytes4 private key_1 = 0x95c8029d;
    bytes16 private key_2 = 0xf07b7fc0b6845e34a4b8a7f3a83ed68f;
    address private owner = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    uint256 private Token = 87;
    address private immutable Investor = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    address private Courier = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    bytes32 private immutable password = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }

    function getImmutableValueStorageSlot() public view returns (uint256) {
        return type(StorageChallenge7).slot("myImmutableValue");
    }




    
}

contract StorageChallenge3 {
    address private owner = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    uint64 private password = 34;
    bytes32 private user = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address[2] private investor;

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }



}

contract StorageChallenge1 {
    bytes32 private user = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address[2] private investor;
    uint64 private password = 34;
    address private owner = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;

    constructor(address investor1, address investor2) {
        investor[0] = investor1;
        investor[1] = investor2;
    }

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }




}

contract StorageChallenge8 {
    bytes32 private key = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    bytes4 private key_1 = 0x95c8029d;
    bytes16 private key_2 = 0xf07b7fc0b6845e34a4b8a7f3a83ed68f;
    address private owner = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    uint256 private Token = 106;
    address private immutable Investor = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    address private Courier = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;
    uint256 private lump_sum = 56;
    bytes32 private password = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }
}



contract StorageChallenge6 {
    bytes32 immutable passphrase = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    uint64 private password = 89;
    bytes32 private user = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address[2] private investor;
    address private owner = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;


    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }

}

contract StorageChallenge9 {
    bytes32 private unique_code = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    bytes32 private key_12 = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address private owner = 0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005;
    address[20] public player;
    bool private valid = true;
    bytes32 private password = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address private enemy = 0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005;
    bool private answered = false;

      constructor() {
        player[0] = address(0x1234567890123456789012345678901234567890);
        player[1] = address(0x9876543210987654321098765432109876543210);
        player[2] = address(0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005);
        player[3] = address(0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005);
        player[4] = address(0x5555555555555555555555555555555555555555);
        player[5] = address(0x7777777777777777777777777777777777777777);
        player[6] = address(0x8888888888888888888888888888888888888888);
        player[7] = address(0x9999999999999999999999999999999999999999);
        player[8] = address(0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005);
        player[9] = address(0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005);
        player[10] = address(0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005);
        player[11] = address(0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005);
        player[12] = address(0xd2a5bC10698FD955D1Fe6cb468a17809A08fd005);
        player[13] = address(0x1111111111111111111111111111111111111111);
        player[14] = address(0x2222222222222222222222222222222222222222);
        player[15] = address(0x3333333333333333333333333333333333333333);
        player[16] = address(0x4444444444444444444444444444444444444444);
        player[17] = address(0x5555555555555555555555555555555555555555);
        player[18] = address(0x6666666666666666666666666666666666666666);
        player[19] = address(0x7777777777777777777777777777777777777777);
    }

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }

}

contract StorageChallenge4 {
    uint64 private password = 65 ;
    bytes32 private user = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address[2] private investor;
    bytes32 immutable  passphrase = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    address private owner = 0x5B38Da6a701c568545dCfcB03FcB875f56beddC4;

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }
}

contract Hell_0 {
    uint256 private avail_money = 1000;
    uint256 private saved_money = 1009;
    bool private not_minus = true;
    address private owner = 0x3328358128832A260C76A4141e19E2A943CD4B6D;
    uint256[2] private geo_loc;
    bool private is_there = false;
    bool private there = true;
    address private wallet = 0x3328358128832A260C76A4141e19E2A943CD4B6D;
    address private receiver = 0x3328358128832A260C76A4141e19E2A943CD4B6D;
    address[20] private transaction_list;
    bytes32 private user_creds = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    uint256 private immutable user_in_uint = 790;
    bytes32 private password = 0x95c8029d0e4c511b8c3a51952d6f1e0f979f7528876d101d4208980133998a04;
    uint256 private password_uint = 56;
    bool private correct_password = true;
    bool private is_user = false;



    constructor() {
        transaction_list[0] = address(0x1234567890123456789012345678901234567890);
        transaction_list[1] = address(0x9876543210987654321098765432109876543210);
        transaction_list[2] = address(0x9876543210987654321098765432109876543210);
        transaction_list[3] = address(0x9876543210987654321098765432109876543210);
        transaction_list[4] = address(0x5555555555555555555555555555555555555555);
        transaction_list[5] = address(0x7777777777777777777777777777777777777777);
        transaction_list[6] = address(0x8888888888888888888888888888888888888888);
        transaction_list[7] = address(0x9999999999999999999999999999999999999999);
        transaction_list[8] = address(0x9876543210987654321098765432109876543210);
        transaction_list[9] = address(0x9876543210987654321098765432109876543210);
        transaction_list[10] = address(0x9876543210987654321098765432109876543210);
        transaction_list[11] = address(0x9876543210987654321098765432109876543210);
        transaction_list[12] = address(0x9876543210987654321098765432109876543210);
        transaction_list[13] = address(0x1111111111111111111111111111111111111111);
        transaction_list[14] = address(0x2222222222222222222222222222222222222222);
        transaction_list[15] = address(0x3333333333333333333333333333333333333333);
        transaction_list[16] = address(0x4444444444444444444444444444444444444444);
        transaction_list[17] = address(0x5555555555555555555555555555555555555555);
        transaction_list[18] = address(0x6666666666666666666666666666666666666666);
        transaction_list[19] = address(0x7777777777777777777777777777777777777777);

        geo_loc[0] = 6;
        geo_loc[1] = 78;
    }

    function getStorageSlotPassword() external view returns (uint _slot){
        assembly{
            //return 0
            _slot:= password.slot
        }
    }
}
```

The flag was: `TCP1P{W00t_w00t_t0_th3_p4rty_47JHbddc}`























