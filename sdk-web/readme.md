# DaVinci SDK for the web


DaVinci SDK is a simple but powerful tool to interact with DaVinci platform in the browser. You can create NFTs or collections, then sell, buy, auction, bid, claim, explore all the platform has to offer and much more.

All you need to do is include the SDK file in your project then call any method like sdk.buy with some data and presto!


```html

<!DOCTYPE html>
<html>
<head>
	<title>DaVinci SDK</title>
</head>
<body>
	<h5>DaVinci SDK Test</h5>
	<button onclick="buyStuff()">BUY NFT</button>
</body>
<script src="./web3.min.js"></script>
<script src="./HarmonyJs.browser.js"></script>
<script src="./davinci-web.js"></script>
<script>
var sdk = null;

function main() {
	sdk = new DaVinciSDK(2);               // 0.local 1.mainnet 2.testnet
	sdk.newWallet(sdk.walletType.harmony); // harmony or metamask
}

async function buyStuff() {
    try {
    	let nft = '0xc9dff7a274f608f844b4041ef0d5cc44d46b5312';
    	let own = '0x8c7d955a7d6568a10cc6d9774e9eae7ff5191bd0';
    	let res = await sdk.buy(nft, own);
    	console.log('Response', res);
    } catch(ex) {
    	console.error('Error', ex);
    }
}

window.onload = main;
</script>
</html>
```

Just like that!
