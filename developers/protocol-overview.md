# Protocol Overview

The protocol consist of five main smart contracts and four of which are the main core of the application. The figure provided below is a high level overview of the Malus protocol and how it works. 

{% hint style="info" %}
Please note that this figure only uses USDC, aUSDC, and mUSDC. Each store has to ability to produce mUSDT and mDAI based on the staked aUSDT and aDAI respectively. 
{% endhint %}

![](../.gitbook/assets/malus-usdc-flow-chart.jpg)

The first four smart contracts we will cover are the main core of the application.

## store.sol

Before getting familiar with the functions, we first need to understand the options available and their associated aTokens and mTokens.

| Option | aToken | mToken |
| :--- | :--- | :--- |
| 0 | aUSDC | mUSDC |
| 1 | aUSDT | mUSDT |
| 2 | aDAI | mDAI |



The following functions are the main function that govern the store implementation. Only the owner of a store is able to call these functions.

```text
function sendERC20(
   address tokenContract, 
   address to, 
   uint256 amount
) 
```

This function can be used to send all ERC20 tokens from the store. Note that sending aTokens requires that only the available amount can be sent. 

| Name | Type | Description |
| :--- | :--- | :--- |
| **tokenContract** | address | The address of the ERC20 smart contract. |
| **to** | address | The address of the tokens are being sent to. |
| **amount** | uint256 | The amount of tokens to send. |



```text
function claimStoreHubBalance(
   uint option
)
```

This function is used to withdraw all the total payment from the store hub and remove any additional stake by the specified aToken. 

| Name | Type | Description |
| :--- | :--- | :--- |
| **option** | uint | The option for the associated aToken. |



```text
function getExtensionStake(
   uint option
)
```

This function is used to return the current extension and amount of stake by aToken associated with a store.  __

| Name | Type | Description |
| :--- | :--- | :--- |
| **option** | uint | The option for the associated aToken. |

\_\_

```text
function addStake(
   uint256 amount,
   uint option
)
```

This function is used to add stake by the selected aToken to the amount already stake.

| Name | Type | Description |
| :--- | :--- | :--- |
| **amount** | uint256 | The amount of stake to add. |
| **option** | uint | The option for the associated aToken. |



```text
function getExtensionCollateral(
   uint option
)
```

 This function is used to return the current extension and amount of collateral by aToken associated with a store.

| Name | Type | Description |
| :--- | :--- | :--- |
| **option** | uint | The option for the associated aToken. |



```text
function provideCollateralRelief(
   uint256 amount, 
   uint256 rate, 
   uint option, 
   bool didAddRelief
)
```

This function is used to add and remove collateral relief based on the selected aToken. 

| Name | Type | Description |
| :--- | :--- | :--- |
| **amount** | uint256 | The amount of collateral relief. |
| **rate** | uint256 | The rate for the collateral relief. |
| **option** | uint | The option for the associated aToken. |
| **didAddRelief** | bool | The boolean value deciding if relief should be added or removed. |



```text
function transferCollateral(
   StoreInterface store, 
   uint256 amount, 
   uint option
)
```

This function is used to transfer collateral to a valid store based on the selected aToken_._

| Name | Type | Description |
| :--- | :--- | :--- |
| **store** | address | The address of the store to send the collateral. |
| **amount** | uint256 | The amount of collateral to transfer.  |
| **option** | uint | The option for the associated aToken. |

\_\_

```text
function sellCollateral(
   StoreInterface store,
   uint256 amount,
   uint256 rate, 
   uint option
)
```

This function is used to sell collateral to a valid store based on the selected aToken_._

| Name | Type | Description |
| :--- | :--- | :--- |
| **store** | address | The address of the store to send the collateral. |
| **amount** | uint256 | The amount of collateral to sell.  |
| **rate** | uint256 | The rate for the collateral to sell. |
| **option** | uint | The option for the associated aToken. |

\_\_

```text
function updateExtension(
   address newExtension
)
```

This functions is used to change the current extension the store is using_._

| Name | Type | Description |
| :--- | :--- | :--- |
| **newExtension** | address | The address of the new Extension that will be added to a store. |

\_\_

```text
function updateOwner(
   address newOwner
)
```

This function is used to change the current owner of the store.

| Name | Type | Description |
| :--- | :--- | :--- |
| **newOwner** | address | The address of the new Owner controlling this store. |

## 

## mUSDC.sol

{% hint style="info" %}
Please note that stores are not meant to hold mTokens. They will be burnt if sent to a store with collateral or the transfer will be rejected. This contracts implements all functions of the ERC20 standard expect the following.
{% endhint %}



```text
function deployStore()
```

This is the main function that is used to deploy new stores in the protocol. The caller will be the owner of the newly deployed store.

| Name | Type | Description |
| :--- | :--- | :--- |
|  |  |  |



```text
function mint(
   StoreInterface store, 
   uint256 tokenID, 
   uint256 amount
)
```

This function is used to pay a store with USDC and mint mUSDC tokens to the customer paying.

| Name | Type | Description |
| :--- | :--- | :--- |
| **store** | address | The address of the store the customer is paying. |
| **tokenID** | uint256 | The ID number to be sent to the store's Extension. |
| **amount** | uint256 | The amount of USDC the customer is paying with. |



```text
function burn(
   StoreInterface store, 
   address from, 
   uint256 tokenID, 
   uint256 amount
)
```

This function is used to pay a store with mUSDC and burn mUSDC token once payed.

| Name | Type | Description |
| :--- | :--- | :--- |
| **store** | address | The address of the store the customer is paying. |
| **from** | address | The address of the customer making the payment. |
| **tokenID** | uint256 | The ID number to be sent to the store's Extension. |
| **amount** | uint256 | The amount of mUSDC the customer is paying with. |





## mUSDT.sol

{% hint style="info" %}
Please note that stores are not meant to hold mTokens. They will be burnt if sent to a store with collateral or the transfer will be rejected. This contracts implements all functions of the ERC20 standard expect the following.
{% endhint %}

## 

## mDAI.sol

{% hint style="info" %}
Please note that stores are not meant to hold mTokens. They will be burnt if sent to a store with collateral or the transfer will be rejected. This contracts implements all functions of the ERC20 standard expect the following.
{% endhint %}

## 

## metadata.sol







