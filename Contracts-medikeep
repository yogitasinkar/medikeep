pragma solidity ^0.4.18;

contract Owned {
    address owner;
    
    function Owned() public {
        owner = msg.sender;
    }
    
   modifier onlyOwner {
       require(msg.sender == owner);
       _;
   }
}

contract Abc is Owned{
    
    struct User {
        uint age;
        bytes16  fName;
        bytes16  lName;
    }
   
    mapping (address = User) users;
    address[] public userAccts;
    
    event UserInfo(
        bytes16 firName,
        bytes16 lasName,
        uint age
        
        );
    
    function setData(address _address, uint _age, bytes16  _fName, bytes16  _lName) onlyOwner public {
        var user = users[_address];

        user.age = _age;
        user.fName = _fName;
        user.lName = _lName;
        
        userAccts.push(_address) -1;
        UserInfo(_fName, _lName, _age);
    }
    
     function getDatas() view public returns (address[]) {
        return userAccts;
    }
    
    function getData(address ad) view public returns (uint, bytes16 , bytes16 ) {
        return (users[ad].age, users[ad].fName, users[ad].lName);
    }
    
    function countUsers() view public returns (uint) {
        return userAccts.length;
    }
}
