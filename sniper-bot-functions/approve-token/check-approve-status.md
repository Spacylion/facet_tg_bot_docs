<h1>🔄 Check Approve Status</h1>

<h2>Introduction</h2>

<p>The <code>checkApproveStatus</code> function is a crucial aspect of interacting with the Sniper Facet Bot. This function allows users to verify the approval status for specific token transfers. Understanding the approval status is vital before executing transactions.</p>

<h2>Purpose</h2>

<p>The primary purpose of the <code>checkApproveStatus</code> function is to provide information about whether a particular token transfer is approved or not. It plays a significant role in ensuring the smooth execution of transactions within the Ethereum blockchain.</p>

<h2>Usage</h2>

<p>To utilize the <code>checkApproveStatus</code> function effectively, users need to consider the following parameters:</p>

<ul>
    <li><code>user_address</code>: The Ethereum address of the user's wallet.</li>
    <li><code>router_address</code>: The address of the Facet Goerli Router.</li>
</ul>

<h2>Response</h2>

<p>The response from the <code>checkApproveStatus</code> function includes details about various liquidity pools, such as:</p>

<ul>
    <li>Token information (address, name, symbol) for token0 and token1 in the pool.</li>
    <li>Liquidity pool reserves for both tokens.</li>
    <li>Total Value Locked (TVL) in Wrapped Ether (WETH).</li>
    <li>User balances for LP, token0, and token1.</li>
    <li>User allowances for LP, token0, and token1.</li>
</ul>

<h3>Example Response</h3>

<pre>
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
</pre>

<h2>Understanding User Allowances</h2>

<p>The <code>user_allowances</code> section in the response indicates the approval status. If the value is <code>0</code>, it means the token transfer is not approved (❌). If the value is a specific number, the transfer is approved (✅).</p>

<p>Ensure that the necessary approvals are in place before proceeding with transactions.</p>

<p>Feel free to explore other functionalities provided by the Sniper Facet Bot in the <a href="link-to-main-doc">main documentation</a>.</p>

<p>Happy trading! 📈</p>
