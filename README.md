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

### Creating an ETH Sell Order 

```Javascript
//Replace constants with your data
const contractErc721Address = ''; // your ERC721 contract address
const tokenId = ''; // the ERC721 Id of the token on which we want to place a bid
const sellerAddress = ''; // Owner of ERC721 token
const nftAmount = 1; // For ERC721 always be 1
const sellPrice = ''; //ETH price in Wei
    
const request = {
    makeAssetType: {
        assetClass: "ERC721",
        contract: contractErc721Address,
        tokenId: tokenId,
    },
    maker: sellerAddress,
    amount: nftAmount,
    originFees: [],
    payouts: [],
    price: sellPrice,
    takeAssetType: {
        assetClass: "ETH"
    }
}

sdk.order.sell(request).then(a => {
    console.log(a);
})

```
