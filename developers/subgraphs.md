# Subgraphs

Developers that wish to query information about stores such as their owners, balances, stats, and metadata are able to so using our subgraphs. You are able to use GraphQL to find all the necessary information you might need.&#x20;

## Malus V1

The first subgraph we are going to explore is Malus V1. This subgraph is used to query data for our simple MVP frontend. You can query this subgraph to find all the information that is displayed on [https://app.malus.fi](https://app.malus.fi).

{% hint style="warning" %}
Please note that as our application grows, there will be different versions of this our subgraph that will be released. You can join us on our discord channel to keep updated with new releases. [https://discord.com/invite/cuXW8gq9kE](https://discord.com/invite/cuXW8gq9kE)
{% endhint %}

### Contracts

These are the main smart contracts which this subgraph is indexing.

| Contract                   | Address                                    | Description |
| -------------------------- | ------------------------------------------ | ----------- |
| **mUSDC**                  | coming soon.                               |             |
| **aUSDC**                  | 0xBcca60bB61934080951369a648Fb03DF4F96263C |             |
| **USDC**                   | 0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48 |             |
| **Metadata**               | coming soon.                               |             |
| **Verification**           | coming soon.                               |             |
| **ENSRegistry**            | 0x00000000000C2E074eC69A0dFb2997BA6C7d2e1e |             |
| **ENSRegistryOld**         | 0x314159265dd8dbb310642f98f50c066173c1259b |             |
| **Resolver**               | 0x4976fb03C32e5B8cfe2b6cCB31c09Ba78EBaBa41 |             |
| **BaseRegistrar**          | 0x57f1887a8BF19b14fC0dF6Fd9B2acc9Af147eA85 |             |
| **EthRegistrarController** | 0x283Af0B28c62C092C9727F1Ee09c02CA627EB7F5 |             |



### Entities&#x20;

These are the main objects you can query using GraphQL to find these necessary information you will need. There are currently only four entities which are User, Store, Domain, and CollateralRelief.





## Malus Recycling

Coming soon.&#x20;



