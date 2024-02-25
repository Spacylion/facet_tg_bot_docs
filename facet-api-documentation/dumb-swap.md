# Dumb swap

## Dumb swap

#### Request

Simulate the swap of initial settings with the following API call:

```http

GET https://sepoloia-api.facet.org/contracts/simulate?from=<from_address>&tx_payload=<tx_payload>
```

\<from\_address>: Ethereum address initiating the simulation. \<tx\_payload>: Transaction payload containing the swap details.

Example:

```
GET https://sepoloia-api.facet.org/contracts/simulate?from=0xb45C39734Cbcc7335DCE837563A535ec3165fB97&tx_payload=%7B%22op%22%3A%22call%22%2C%22data%22%3A%7B%22to%22%3A%220xb324c3fccd5da0bad69d2709752044c6bd9adf1f%22%2C%22function%22%3A%22swapExactTokensForTokens%22%2C%22args%22%3A%7B%22path%22%3A%5B%220xcffc7fbd459d4c028163029d0db0fa26f44b0ed1%22%2C%220xb51fda5801f336d6038d555f4da6a4e2778be5dc%22%5D%2C%22deadline%22%3A%221000000000000000000%22%2C%22to%22%3A%220x799878bEf1fbA6216A5Ceb83e62c046Fb9ed0B1b%22%2C%22amountIn%22%3A%2299300000000000%22%2C%22amountOutMin%22%3A%220%22%7D%7D%7D
```

Response The response provides details about the simulated transaction, including the transaction hash, status, and event logs.

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

status: Transaction status (success/error). amountIn: Amount of input tokens. amountOutMin: Minimum amount of output tokens. ethscription\_content\_uri: URI for Ethereum transaction content.

### Simulation for Swap with Modified amountOutMin

## Request

Simulate a swap with a modified amountOutMin using the following API call:

```
GET https://sepoloia-api.facet.org/contracts/simulate?from=<from_address>&tx_payload=<tx_payload>
```

\<from\_address>: Ethereum address initiating the simulation. \<tx\_payload>: Transaction payload with modified amountOutMin.

Example:

```
GET https://sepoloia-api.facet.org/contracts/simulate?from=0x799878bEf1fbA6216A5Ceb83e62c046Fb9ed0B1b&tx_payload=%7B%22op%22%3A%22call%22%2C%22data%22%3A%7B%22to%22%3A%220xb324c3fccd5da0bad69d2709752044c6bd9adf1f%22%2C%22function%22%3A%22swapExactTokensForTokens%22%2C%22args%22%3A%7B%22path%22%3A%5B%220xcffc7fbd459d4c028163029d0db0fa26f44b0ed1%22%2C%220xb51fda5801f336d6038d555f4da6a4e2778be5dc%22%5D%2C%22deadline%22%3A%221000000000000000000%22%2C%22to%22%3A%220x799878bEf1fbA6216A5Ceb83e62c046Fb9ed0B1b%22%2C%22amountIn%22%3A%2299300000000000%22%2C%22amountOutMin%22%3A%2230167189699552920000%22%7D%7D%7D
```

### Response

The response structure remains consistent with the initial settings simulation.

```
{
    "result": {
        "transaction_receipt": {
            "transaction_hash": "0x70b91127362bb6db60e796345ffefe1e228a97388d906a11a4332bbd487461f4",
            "status": "failure",
            "function": "swapExactTokensForTokens",
            "args": {
                "path": [
                    "0xcffc7fbd459d4c028163029d0db0fa26f44b0ed1",
                    "0xb51fda5801f336d6038d555f4da6a4e2778be5dc"
                ],
                "deadline": "1000000000000000000",
                "to": "0x799878bEf1fbA6216A5Ceb83e62c046Fb9ed0B1b",
                "amountIn": "99300000000000",
                "amountOutMin": "30167189699552920000"
            },
            "logs": [],
            "block_timestamp": "1705745650",
            "error": {
                "message": "EtherBridge error: Insufficient balance. (ERC20:30)"
            },
            "effective_contract_address": "0xb324c3fccd5da0bad69d2709752044c6bd9adf1f",
            "block_number": "10404289",
            "transaction_index": "1",
            "block_blockhash": "0x4371b97443d1f193b2c908a6c329847ac79822d746f8990c0027e0440edc80b2",
            "return_value": null,
            "runtime_ms": "20",
            "call_type": "call",
            "gas_price": null,
            "gas_used": null,
            "transaction_fee": null,
            "to": "0xb324c3fccd5da0bad69d2709752044c6bd9adf1f",
            "from": "0x799878bef1fba6216a5ceb83e62c046fb9ed0b1b",
            "contract_address": null,
            "to_or_contract_address": "0xb324c3fccd5da0bad69d2709752044c6bd9adf1f"
        },
        "ethscription_status": "success",
        "ethscription_error": null,
        "ethscription_content_uri": "data:application/vnd.facet.tx+json;rule=esip6,{\"op\":\"call\",\"data\":{\"to\":\"0xb324c3fccd5da0bad69d2709752044c6bd9adf1f\",\"function\":\"swapExactTokensForTokens\",\"args\":{\"path\":[\"0xcffc7fbd459d4c028163029d0db0fa26f44b0ed1\",\"0xb51fda5801f336d6038d555f4da6a4e2778be5dc\"],\"deadline\":\"1000000000000000000\",\"to\":\"0x799878bEf1fbA6216A5Ceb83e62c046Fb9ed0B1b\",\"amountIn\":\"99300000000000\",\"amountOutMin\":\"30167189699552920000\"}}}"
    }
}
```

### Transaction on Ethereum Blockchain

After obtaining the optimized ethscription\_content\_uri, make a transaction on the Ethereum blockchain to the 0x00000...face7 address with 0 tokens. The ethscription\_content\_uri should be provided in hex format.

This documentation provides a comprehensive guide to facet API calls related to simulations and transactions. Ensure to use the appropriate endpoints and parameters for successful interaction with the Facet protocol.
