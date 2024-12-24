# SC_UEE
A benchmark dataset contains 4,364 real-world Solidity smart contracts, which are manually labeled with ten types of vulnerabilities.

## DC (DelegateCall).
The address.delegatecall() function allows a smart contract to dynamically load external contracts from address at runtime. If the attacker can control the external contract and affect the current contract status, the contract is vulnerable to DC.

## IOU (Arithmetic/Integer Overflow and Underflow).
An arithmetic overflow or underflow, often called Integer Overflow or Underflow (IOU), occurs when an arithmetic operation attempts to create a numeric variable value that is larger than the maximum value or smaller than the minimum value of the variable type. If the arithmetic operation may pass a variable type’s maximum or minimum value and  is performed without using SafeMath, the contract is vulnerable to IOU.

## NC (Nested Call).
The function containing the loop has a high risk of exceeding its gas limitation and causing an out-of-gas error. If the attacker can control the loop iteration and causes the out-of-gas error, the contract is vulnerable to NC, 

## RE (Reentrancy).
The contract vulnerable to RE uses the call() function to transfer ether to an external contract. The external contract can reenter the vulnerable contract by fallback function. If the state variable change is after the call() function, the reentrance will cause status inconsistency. 

## TD (Timestamp Dependency).
The contract uses the timestamp as the deciding factor for critical operations, e.g., sending ether. If the attacker can get ether from the contract by manipulating the timestamp or affecting the critical operations, the contract is vulnerable to TD.

## TO (TxOrigin).
If the contract only uses tx.origin to verify the caller's identification for critical operations, it is vulnerable to TO.

## TOD (Transaction Order Dependency).
The contract may send out ether differently according to different values of a global state variable or different balance values of the contract. If the attackers can get ether from the contract by manipulating the transaction sequences, the contract is vulnerable to TOD.

## UcC (Unchecked Call).
The contract uses the function call() or send() without result checking. If the send() or call()  function fails and leads to status inconsistency, the contract is vulnerable to UcC.

## UpS (Unprotected Suicide).
If an attacker can self-destruct the contract by calling the selfdestruct(address) function, the contract is vulnerable to UpS. 

## FE (Frozen Ether).
If the contract can receive ether but cannot transfer it by itself, it is vulnerable to FE. 



