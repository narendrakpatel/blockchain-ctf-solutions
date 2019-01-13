# Concept
After reading code of the smart Contract Donation, we can see the following function:
```
function withdrawDonationsFromTheSuckersWhoFellForIt() external ctf{
    msg.sender.transfer(funds);
    funds = 0;
}
```
A simple call to this function will result in transfer of 'funds' from the contract to our account.