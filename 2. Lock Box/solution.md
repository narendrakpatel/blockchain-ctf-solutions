# Solution

1. Open console in your web browser.


2. Enter following code with proper parameters in the console.
```javascript
web3.eth.getStorageAt(challengeAddressString, 1, console.log)
```
3. Convert the output from hexadecimal value to decimal.

4. Load contract in MyCrypto.

5. Make a transcation to ```unlock(uint256 _pin)``` with ```_pin``` as the decimal value obtained above.
