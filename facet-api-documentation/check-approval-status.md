 <h1>Check Approval Status API</h1>

  <p>
    The Check Approval Status API provides endpoints to check the approval status for token transfers.
    Ensure that you have the necessary approvals before proceeding with transactions.
  </p>

  <h2>Endpoints</h2>

  <h3>1. Check User Allowance</h3>
  <p>
    <strong>Endpoint:</strong> <code>GET /contracts/user_allowance</code><br>
    <strong>Query Parameters:</strong>
    <ul>
      <li><code>user_address:</code> Ethereum address of the user's wallet.</li>
      <li><code>router:</code> Address of the Facet Goerli Router.</li>
    </ul>
  </p>

  <h4>Example:</h4>
  <pre>
    <code>
      GET /contracts/user_allowance?user_address=0xAC4e62DCB0d074f496055d500F9530986a08D7a1&router=0xb324c3fccd5da0bad69d2709752044c6bd9adf1f
    </code>
  </pre>

  <p>
    The response will contain information about the user's approval status for token transfers.
    If the value is <code>0</code>, the transfer is not approved (❌).
    If the value is a specific number, the transfer is approved (✅).
  </p>

  <h2>Code Example</h2>
  <p>
    Here's a sample JavaScript code snippet using axios to make the API call:
  </p>

  <pre>
    <code>
      const axios = require('axios');

      const userAddress = '0xAC4e62DCB0d074f496055d500F9530986a08D7a1';
      const routerAddress = '0xb324c3fccd5da0bad69d2709752044c6bd9adf1f';

      axios.get(`https://goerli-api.facet.org/contracts/user_allowance?user_address=${userAddress}&router=${routerAddress}`)
        .then(response => {
          console.log(response.data);
        })
        .catch(error => {
          console.error('Error:', error);
        });
    </code>
  </pre>
