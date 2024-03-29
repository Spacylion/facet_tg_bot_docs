# 🔍 Check Approve Status

## Introduction

The `checkApproveStatus` function is a critical aspect of interacting with the Sniper Facet Bot. This function allows users to verify the approval status for specific token transfers. Understanding the approval status is vital before executing transactions.

## Purpose

The primary purpose of the `checkApproveStatus` function is to provide information about whether a particular token transfer is approved or not. It plays a significant role in ensuring the smooth execution of transactions within the Ethereum blockchain.

## Usage

To utilize the `checkApproveStatus` function effectively, users need to consider the following parameters:

* `user_address`: The Ethereum address of the user's wallet.
* `router_address`: The address of the Facet Goerli Router.

### Endpoint

* **Endpoint**: `POST https://goerli-api.facet.org/contracts/pairs_for_router`
* **Query Parameters**:
  * `user_address`: Ethereum address of the user's wallet.
  * `router`: Address of the Facet Goerli Router.

## Response

The response from the `checkApproveStatus` function includes details about various liquidity pools, such as:

* Token information (address, name, symbol) for token0 and token1 in the pool.
* Liquidity pool reserves for both tokens.
* Total Value Locked (TVL) in Wrapped Ether (WETH).
* User balances for LP, token0, and token1.
* User allowances for LP, token0, and token1.

### Example Response

```json
{
    "0x7649387adbecf66aec55703fe36b77a46deb92ef": {
        // Details for liquidity pool 1
        // ...
    },
    "0xcf77e44513eaf1b13c01c03dacad207dcbf64c18": {
        // Details for liquidity pool 2
        // ...
    },
    "0xe35143750179ed873b8a0e5c33e8ae3571b6b984": {
        // Details for liquidity pool 3
        // ...
    }
}
```

## Understanding User Allowances

The `user_allowances` section in the response indicates the approval status. If the value is `0`, it means the token transfer is not approved (❌). If the value is a specific number, the transfer is approved (✅).

Ensure that the necessary approvals are in place before proceeding with transactions.

For Facet API documentation, you can also perform token approval transactions using the provided `handleApproveTokenTransaction` function. The endpoint for simulating this transaction is:

* **Endpoint:** `POST https://goerli-api.facet.org/contracts/simulate`
* **Query Parameters:**
*
  * `from:` Ethereum address of the user's wallet.

Feel free to explore other functionalities provided by the Sniper Facet Bot in the [main documentation](link-to-main-doc/).
