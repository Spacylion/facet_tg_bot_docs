# Dumb swap

### Request

Simulate the swap of initial settings with the following API call:

```http

GET https://goerli-api.facet.org/contracts/simulate?from=<from_address>&tx_payload=<tx_payload>
```
<from_address>: Ethereum address initiating the simulation.
<tx_payload>: Transaction payload containing the swap details.


Example: 
```
GET https://goerli-api.facet.org/contracts/simulate?from=0xb45C39734Cbcc7335DCE837563A535ec3165fB97&tx_payload=%7B%22op%22%3A%22call%22%2C%22data%22%3A%7B%22to%22%3A%220xb324c3fccd5da0bad69d2709752044c6bd9adf1f%22%2C%22function%22%3A%22swapExactTokensForTokens%22%2C%22args%22%3A%7B%22path%22%3A%5B%220xcffc7fbd459d4c028163029d0db0fa26f44b0ed1%22%2C%220xb51fda5801f336d6038d555f4da6a4e2778be5dc%22%5D%2C%22deadline%22%3A%221000000000000000000%22%2C%22to%22%3A%220x799878bEf1fbA6216A5Ceb83e62c046Fb9ed0B1b%22%2C%22amountIn%22%3A%2299300000000000%22%2C%22amountOutMin%22%3A%220%22%7D%7D%7D
```

Response
The response provides details about the simulated transaction, including the transaction hash, status, and event logs.
```
{
    "result": {
        "transaction_receipt": {
            // Transaction details...
        },
        "ethscription_status": "success",
        "ethscription_error": null,
        "ethscription_content_uri": "data:application/vnd.facet.tx+json;rule=esip6,{...}"
    }
}
```
Extracted information includes:

status: Transaction status (success/error).
amountIn: Amount of input tokens.
amountOutMin: Minimum amount of output tokens.
ethscription_content_uri: URI for Ethereum transaction content.

## Simulation for Swap with Modified amountOutMin
# Request
Simulate a swap with a modified amountOutMin using the following API call:
```
GET https://goerli-api.facet.org/contracts/simulate?from=<from_address>&tx_payload=<tx_payload>
```
<from_address>: Ethereum address initiating the simulation.
<tx_payload>: Transaction payload with modified amountOutMin.

Example:
```
GET https://goerli-api.facet.org/contracts/simulate?from=0xb45C39734Cbcc7335DCE837563A535ec3165fB97&tx_payload=%7B%22op%22%3A%22call%22%2C%22data%22%3A%7B%22to%22%3A%220xb324c3fccd5da0bad69d2709752044c6bd9adf1f%22%2C%22function%22%3A%22swapExactTokensForTokens%22%2C%22args%22%3A%7B%22path%22%3A%5B%220xcffc7fbd459d4c028163029d0db0fa26f44b0ed1%22%2C%220xb51fda5801f336d6038d555f4da6a4e2778be5dc%22%5D%2C%22deadline%22%3A%221000000000000000000%22%2C%22to%22%3A%220xb45C39734Cbcc7335DCE837563A535ec3165fB97%22%2C%22amountIn%22%3A%221000000000000000%22%2C%22amountOutMin%22%3A0%7D%7D%7D
```
## Response
The response structure remains consistent with the initial settings simulation.

## Transaction on Ethereum Blockchain
After obtaining the optimized ethscription_content_uri, make a transaction on the Ethereum blockchain to the 0x00000...face7 address with 0 tokens. The ethscription_content_uri should be provided in hex format.

This documentation provides a comprehensive guide to facet API calls related to simulations and transactions. Ensure to use the appropriate endpoints and parameters for successful interaction with the Facet protocol.

