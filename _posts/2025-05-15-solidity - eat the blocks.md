
```sol
// SPDX-License-Identifier: MIT

pragma solidity ;

  
  

// for general layout of solidity

contract MyContract {
unit a ;
unit b ;
function add() external {
return a + b ;
}  
}
```



----
## about Variables -> 

```solidity
// SPDX-License-Identifier: MIT
pragma solidity >=0.7.0 <0.9.0;

// for general layout of solidity

contract MyContract {
	
	// 1. fixed size types
	
	bool isReady;
	uint a; // unsigned integer -> for transactions and all
	address recipent;	
	bytes32 data; // used to represent strings

	
	// 2. variable size types 0-> for variable memory
	string name; //can be of anylength
	bytes _data; //this doesnt have defined length	
	uint[] amounts;
	mapping(uint => string) users;

  

// 3. user defined data
	struct User {
		uint id;
		string name;
		uint[] friends;
}

	enum Color {
		RED,
		GREEN,
		BLUE
		}// FOR LABELIING OF THE

}
```



### functions in Solidity

```solidity
// SPDX-License-Identifier: MIT

pragma solidity >=0.7.0 <0.9.0;

// for general layout of solidity

contract MyContract{
	uint value;
	function getValue() external view returns(uint)
		{
		return value;
		}

//to change value variable inside blockchain

	function setValue(uint _value) external
		{ 
		/*we removed view keyword so that we could change the value
		value = _value;
		}

}
```


###  Interacting with a Smart Contract with Remix 

![[Pasted image 20250121112344.png]]

![[Pasted image 20250121112523.png]]


-- after updating the value we could also getValue of the setValue

![[Pasted image 20250121112613.png]]


###  Function modifier keywords (view, pure, constant)

![[Pasted image 20250121112729.png]] 
if you have set variable to view then you could'nt modify the variable value so thats why we are recieving an error 

- `view` keyword makes the function as readonly 

API's to interact with smart contracts 
- `eth_pure`
- `eth_send`


###  Function visibility (external, public, internal & private)

1. Private
![[Pasted image 20250122191906.png]]

How to decide which is best for you ?
- you can't use public keyword for every function as , i could create a vulnerablilty insie the smart contract 

2. External
![[Pasted image 20250122192144.png]] 



### Variable Visibility (private, internal & public)

```solidity
// SPDX-License-Identifier: MIT
pragma solidity >=0.7.0 <0.9.0;

contract MyContract {

	uint private a;
	function foo() external {
		uint b = a + 1;
	}
}
```

- visiblilty can be decided when you give the least privelege to the variable 


even we havent declared any function a still its givving errors 

![[Pasted image 20250122194121.png]]

### Built-in Variables (msg.sender, msg.value...)

- you can get the information about your environment 


```solidity
  
contract MyContract{

//tx
	tx.origin

//msg
	msg.value
	msg.sender

  

	Alice => Smart contract A => Smart contract B => C
			 tx.origin=Alice tx.origin=Alice
			 msg.sender=Alice msg.sender=Smart contract A

//block added during mining process
	block.timestamp / now => 1970(s)

}
```


### control structures (if , for loop , while)

```solidity

contract MyContract {
	function foo() external {
		if(! boolValue){
		}else{
		}
	}
}
```


```sol
contract MyContract {
	function foo() external {
		if(! boolValue){
		}else{
		}
	}
}
```



### Arrays (Declare , Read , Update , Delete)

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.5.17;

contract MyContract{
    /*1 storing arrays 
     2. memory arrays 
     3. arrasys arguments and returns arrays from the functions 

     */

     uint[] myArray;

     function food() external {
        myArray.push(2);
        myArray.push(3);

//reading element
        myArray[0];
        myArray[1];

//updating the values
        myArray[0]=20;

//deleting the values ; just reset the values to the zero
        delete myArray[1];
        
     }
}
```




### Mappings 
In **Solidity**, a **mapping** is a reference type that acts like a **hash table or dictionary**. It allows you to associate **key-value pairs**, where each key maps to a corresponding value. Mappings are widely used in smart contracts for storing structured data like user balances, ownership records, permissions, etc

```solidity
pragma solidity ^0.5.11;
contract MyContract {
	/*1. declare mappings
	2. C.R.U.D
	3 Default values
	3. Exotic mapping 1: nested mappings
	4. Exotic mapping 2: array inside mapping*/
	{	
	a: 1,
	b: 2
	}
}

```


```solidity
mapping(keyType => valueType) visibility variableName;
```

- `keyType`: Can be any built-in value type (like `address`, `uint`, `bytes32`, etc.), but **not** a complex type like another mapping or struct.  
- `valueType`: Can be any type, including other mappings or structs.


```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.5.17;

contract MyContract {
    // 1. Declare mappings
    mapping(address => uint) balances;
    mapping(address => mapping(address => bool)) public isFriend;

    function foo(address someAddressThatDoesNotExist) external {
        // 2. Add / Write
        balances[msg.sender] = 100;

        // 2. Read (use variable to demonstrate)
        uint myBalance = balances[msg.sender];

        // 2. Update
        balances[msg.sender] = 200;

        // 2. Delete
        delete balances[msg.sender];

        // 3. Default value (returns 0 if the address doesn't exist)
        uint defaultValue = balances[someAddressThatDoesNotExist];  // = 0

        // 4. Exotic mapping example - nested mapping usage
        isFriend[msg.sender][someAddressThatDoesNotExist] = true;
    }
}
```



### Structs

In **Solidity**, a **struct** is a **custom data type** that lets you group multiple variables into a single, logical unit. Structs are useful for organizing and managing related data.

---

Why Use Structs?
Structs help manage **complex data** by combining related properties. For example, instead of storing names, ages, and addresses in separate mappings, you can combine them in a single struct called `Person`

#### Where Can Structs Be Used?

- Inside mappings
- Inside arrays
- As function parameters and return types
- Inside other structs (nested structs)

1. Declare struct
2. create read update and delete
3. array of struct
4. mapping of struct


```solidity
struct StructName {
    dataType1 property1;
    dataType2 property2;
    ...
}
```

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MyContract {
    // Define a struct
    struct Person {
        string name;
        uint age;
        address wallet;
    }

    // Use struct in a mapping
    mapping(address => Person) public people;

    function addPerson(string memory _name, uint _age) public {
        people[msg.sender] = Person(_name, _age, msg.sender);
    }

    function getPerson() public view returns (string memory, uint, address) {
        Person memory p = people[msg.sender];
        return (p.name, p.age, p.wallet);
    }
}

```