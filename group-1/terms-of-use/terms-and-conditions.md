# 📃 ETH and FETH Fetching:

We used Web3.js to interact with the Ethereum blockchain and fetch ETH-related data.

```
// const Web3 = require('web3');
const web3 = new Web3(alchemy.getHttpProvider());

// Fetch ETH wallet address
const walletAddress = await web3.eth.getAccounts();

// Fetch other ETH-related data as needed
// ...

```

