# Concept

After reading the code of the smart contract, we can see the following functions:
```
contract PiggyBank is CtfFramework {
    // ...
    function collectFunds(uint256 amount) public onlyOwner ctf{
        // ...
    }
}

contract CharliesPiggyBank is PiggyBank {
    // ...
    function collectFunds(uint256 amount) public ctf{
        // ...
    }
}
```
We can see that there is polymorphism at play. Thus, ```collectFunds``` from ```CharliesPiggyBank``` can be called from any address as it does not have the ```onlyOwner``` modifier.

A simple call to the function ```collectFunds``` from with ```amount = 0.15 Ether``` will result in transfer of funds from contract to our account.
