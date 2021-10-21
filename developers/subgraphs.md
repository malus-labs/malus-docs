# Subgraphs

Developers that wish to query information about stores such as their owners, balances, stats, and metadata are able to so using our subgraphs. You are able to use GraphQL to find all the necessary information you might need.&#x20;

## Malus V1

The first subgraph we are going to explore is Malus V1. This subgraph is used to query data for our simple MVP frontend. You can query this subgraph to find all the information that is displayed on [https://app.malus.fi](https://app.malus.fi).

{% hint style="warning" %}
Please note that as our application grows, there will be different versions of this our subgraph that will be released. You can join us on our discord channel to keep updated with new releases. [https://discord.com/invite/cuXW8gq9kE](https://discord.com/invite/cuXW8gq9kE)
{% endhint %}

### Contracts

These are the main smart contracts which this subgraph is indexing.

| Contract                   | Address                                    | Description                                                                                                                    |
| -------------------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------ |
| **mUSDC**                  | coming soon.                               | The main contract for Malus's mUSDC token and where all stores are deployed.                                                   |
| **aUSDC**                  | 0xBcca60bB61934080951369a648Fb03DF4F96263C | The main contract for Aave's Version 2 aUSDC Token.                                                                            |
| **USDC**                   | 0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48 | The main contract for the USDC token.                                                                                          |
| **Metadata**               | coming soon.                               | The contract where all store's metadata gets updated.                                                                          |
| **Verification**           | coming soon.                               | The contract where verification is added and removed for all ENS names.                                                        |
| **ENSRegistry**            | 0x00000000000C2E074eC69A0dFb2997BA6C7d2e1e | The main contract for all ENS lookups and subdomain nodes.                                                                     |
| **ENSRegistryOld**         | 0x314159265dd8dbb310642f98f50c066173c1259b | The old ENS registry contract for all earlier names.                                                                           |
| **Resolver**               | 0x4976fb03C32e5B8cfe2b6cCB31c09Ba78EBaBa41 | The main contract that is the public resolver for all ENS names.                                                               |
| **BaseRegistrar**          | 0x57f1887a8BF19b14fC0dF6Fd9B2acc9Af147eA85 | The base registrar contract that is called by the EthRegistrarController to transfer ownership of a ENS name to the new owner. |
| **EthRegistrarController** | 0x283Af0B28c62C092C9727F1Ee09c02CA627EB7F5 | The main contract where all new ENS names are registered.                                                                      |





### Entities&#x20;

These are the main objects you can query using GraphQL to find these necessary information you will need. There are currently only four entities which are User, Store, Domain, and CollateralRelief.

####

#### User

This entity is for all current and previous owners who had control of a store.

| Name   | Type | Description                     |
| ------ | ---- | ------------------------------- |
| **id** | ID   | The wallet address of the owner |





#### Domain

This entity is for all ENS names that were created.

| Name           | Type    | Description                                                           |
| -------------- | ------- | --------------------------------------------------------------------- |
| **id**         | ID      | The node of the ENS name.                                             |
| **labelName**  | String  | This is the ENS name without its parent name.                         |
| **name**       | String  | This is the actually ENS name                                         |
| **store**      | Store   | The Store that belongs to this ENS name                               |
| **isVerified** | Boolean | The Boolean value letting us know if a store's ENS name is verified.  |





#### Store

This entity is for all new stores that are deployed in the Malus Protocol.

{% hint style="info" %}
Please note that the available aToken balances are not present in the Store entity. This is mainly because no events are emitted from the aUSDC contract while interest is accruing.
{% endhint %}

| Name                 | Type   | Description |
| -------------------- | ------ | ----------- |
| **id**               | ID     |             |
| **owner**            | User   |             |
| **creationDate**     | BigInt |             |
| **ensName**          | Domain |             |
| **address**          | String |             |
| **availableUSDC**    | BigInt |             |
| **stake**            | BigInt |             |
| **collateral**       | BigInt |             |
| **collateralRelief** | BigInt |             |
| **extension**        |        |             |
| **country**          |        |             |
| **city**             |        |             |
| **street**           |        |             |
| **website**          |        |             |
| **type**             |        |             |
| **zipcode**          |        |             |





#### ColleteralRelief

This entity is used to for Collateral Relief that was previously or currently up for sale by another store.&#x20;

{% hint style="info" %}
Please note that a rate of zero means the Collateral Relief order was already filled or canceled by a store.&#x20;
{% endhint %}

| Name       | Type   | Description                                                             |
| ---------- | ------ | ----------------------------------------------------------------------- |
| **id**     | ID     | The id for the Collateral Relief which is the store's id plus the rate. |
| **rate**   | BigInt | The rate at which the Collateral Relief is selling.                     |
| **amount** | BigInt | The amount of collateral Relief a store owner is selling.               |
| **store**  | Store  | The store that is selling the Collateral Relief.                        |





## Malus Recycling

Coming soon.&#x20;



