# Extensions

Extensions will be extremely important for sellers wishing to perform additional task after receiving payments. They are essentially a smart contract that is called to perform minimal tasks. They can be used for a wide range of activities such as sending NFTs to a customer. 

{% hint style="warning" %}
Please note that adding Extensions to a store will cost the customer additional gas to perform a transaction. The responsibility falls on the developer of the Extension to ensure that the gas cost is optimal.  
{% endhint %}

### 

### Example

```javascript
pragma solidity ^0.8.4;
//SPDX-License-Identifier: MIT


contract Extension {

    /// @param customer The address of the customer who made the payment
    /// @param tokenID The id of the ERC721 token the customer paid for
    /// @param amount The amount in customer paid for the item
    function processPayment(address customer, uint256 tokenID, uint256 amount) external {
        //require(msg.sender == ) IMPORTANT!! check that sender is the corrent mToken contract.
        
        /**
         * Write code to perform additional task after receiving payment
         * such as sending NFTs and checking the amount sent.
        **/
    }
}
```

This is a simple example of an Extension that is suppose to implement the _processPayment\(\)_ function. In addition, If you are using extensions for NFTs, one suggestion would be to use one Extension to manage multiple NFTs. This could help to change ownership on the extension rather than calling multiple different ERC721 contracts. It would reduce the gas cost on customers and avoid creating an Extension for each NFT. The way to achieve this is by mapping the \_tokenID parameter to a struct. The struct could contain other information such as the NFT contract address, tokenID, and amount required for payment. 



