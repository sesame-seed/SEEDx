# Sesameseed Token Swap Service (Ontology)
Price discovery market for swapping tokens.

## Currently Supports:
 
  ONT/ONG 
  
  SEED/ONT
  
  SEED/ONG

## Description

This is a simple price discovery smartcontract for buying and selling of tokens on the Ontology blockchain. These associated contracts operate as "single sided" exchange in which a user interacts directly with the smart contract(s) to buy/sell accroding to a pair. 

The method by this works is based a liquidity pool, which is created and held by the smart contract. Based on factors including liquidty of the representative tokens, total circulating supply of those tokens and market velocity the price is automatically adjusted by the contract itself. 

This system ensurers a purchase or sale to be matched to any order placed by the user by the contract itself so long as basic requirements are met.

These requirements include:
  1. Maximum Transaction - Currently there is a maximum transaction set on the Pair based on the "trading" token (Trading token / Base Token). The contract will not complete if the user inputs a value that will return a result that exceeds 1% of the liquidity pool of the trading token.
  2. Price - A price cannot be set by the user and is calculated in real time based on the current state of the contract. 

### How to Use
  1. Select the Trading Pair you wish to use (Trading/Parent)
    a. BUY: Input a quantity of the Parent (2nd) token
    b. Sell: Input a quantity of the Trading (1st) token
  2. A FEE is calculated in the Parent token.
  3. Upon Execution the trade is immediately completed so long as the above requirements are met. 

## Precision

* ONT : 1 = 1
* ONG : 1 = 1 000 000 000
* SEED :1 = 1 000 000

## Definitions


## Functions

### Owner Functions
* Init() - Initialize the Contract
* SetAdmin(param, address) - [param, address (base58)]

### Admin Functions
* DepositSupply(address, amount, token) - [address (base58), amount (int), token (string)]
* SetTokenData(field, data) - [field (string), data (int)]

### Controller Functions
* WithdrawSupply(address, amount, token) - [address (base58), amount (int), token (string)] 

### Public Functions
* GetTokenData(field) - [field (string)]
#### Fields Accepted
   - Factor    - Returns: Generates current [Price, MaxTransaction]
   - ALL       - Returns: Pulls current [MaxRatio, MaxTransaction, FEE, Price]

### ONT/ONG
* Buy_ONT_ONG(address, amount) - [address (base58), amount (int)]
* Sell_ONT_ONG(address, amount) - [address (base58), amount (int)]

## Contact
For more information please contact Sesameseed or visit us on telegram 
