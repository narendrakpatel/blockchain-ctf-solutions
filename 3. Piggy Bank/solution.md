# Solution

1. Load the contract in MyCrypto.

2. Make a transaction to ```collectFunds(uint256 amount)``` with ```amount``` equal to 150000000000000000.
> Note: We are using '150000000000000000' because ```msg.sender.transfer()``` accepts arguments in wei, not ether.

3. Confirm the Transaction.
