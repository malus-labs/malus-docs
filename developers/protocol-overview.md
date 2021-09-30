# Protocol Overview

The protocol consist of six main smart contracts and four of which are the main core of the application. The figure provided below is a high level overview of the Malus protocol and how it works. 

{% hint style="info" %}
Please note that this figure only uses USDC, aUSDC, and mUSDC. Each store has to ability to produce mUSDT and mDAI based on the staked aUSDT and aDAI respectively. 
{% endhint %}

![](../.gitbook/assets/malus-usdc-flow-chart.jpg)

The first three smart contracts we will cover are the main core of the application.

## store.sol

This is the implementation of the main store smart contract. 

* _sendERC20\(\)_  ****_-_  This function can be used to send all ERC20 tokens from the store. Note that sending aTokens requires that only the available amount can be sent. 



* _claimStoreHubBalance\(\)  -_  This function is used to withdraw all the total payment from the store hub and remove any additional stake by the specified aToken. 



* _getExtensionStake\(\)  -_  This function is used to return the current extension and amount of stake by aToken associated with a store.  __

\_\_

* _addStake\(\)_  -  This function is used to add stake by the selected aToken to the amount already stake.

 

* _getExtensionCollateral\(\)   -_  This function is used to return the current extension and amount of collateral by aToken associated with a store.



* _provideCollateralRelief\(\)_  -  This function is used to add and remove collateral relief based on the selected aToken. 



* _transferCollateral\(\)_  -  __This function is used to transfer collateral to a valid store based on the selected aToken_._

\_\_

* _sellCollateral\(\)  -_  This function is used to sell collateral to a valid store based on the selected aToken_._

\_\_

* _updateExtension\(\)  -_  This functions is used to change the current extension the store is using_._

\_\_

* _updateOwner\(\)_  -  This function is used to change the current owner of the store.

## mUSDC.sol

{% hint style="info" %}
Please not that this contracts implements all functions of the ERC20 standard expect the following. 
{% endhint %}



## mUSDT.sol

{% hint style="info" %}
Please not that this contracts implements all functions of the ERC20 standard expect the following. 
{% endhint %}



## mDAI.sol

{% hint style="info" %}
Please not that this contracts implements all functions of the ERC20 standard expect the following. 
{% endhint %}

## metadata.sol



## verification.sol



