# Concept

After reading the code of the smart contract, we see the following line:

```
feeAmount = 10 szabo; 

function purchaseTokens(uint256 _value) internal{
        require(_value > 0, "Cannot Purchase Zero Tokens");
        require(_value < balances[this], "Not Enough Tokens Available");
      * balances[msg.sender] += _value - feeAmount; *
        balances[this] -= _value;
        balances[developer] += feeAmount; 
        etherCollection += msg.value;
    }
    
function () payable external ctf{
        purchaseTokens(msg.value);
    }
```

We can see that there is underflow detected while reducing the ```feeAmount``` from the ```_value```.
Though the ```purchaseTokens``` is internal we cannot call that function directly but a ```fallback``` can.

A simple transaction call with a ```msg.value``` of (1 x 10^13)-1 will make the 1st objective.

```
    // Allow users to refund their tokens for half price ;-)
    function refundTokens(uint256 _value) external ctf{
        require(_value>0, "Cannot Refund Zero Tokens");
        transfer(this, _value);
        etherCollection -= _value/2;
        msg.sender.transfer(_value/2);
    }

```

The chief part is to retrieve the Contract balance to do that we call ```refundTokens``` with a value twice the balance because of the half price refund.
This will result in transfer of funds from contract to our account.
