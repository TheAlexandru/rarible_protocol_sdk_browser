# Rarible protocol SDK - browser version.
### **Not official, for testing purposes only!**

## Ho to use
1) Add the script file to your app.

```
<script src="./rarible_sdk_browser.js"></script>
```

2) Create the Rarible SDK object in the same way it is shown in the official documentation [here](https://github.com/rarible/protocol-ethereum-sdk/tree/master/packages/protocol-ethereum-sdk). 

The SDK is available globally in the window object.

### Simplified example using MetaMask

```Javascript
if (ethereum && ethereum.isMetaMask) {
    const web3 = new Web3(window.ethereum);
    const sdk = window.createRaribleSdk(web3, 'rinkeby');
}else{
    console.log('MetaMask is not installed!')
}
```
