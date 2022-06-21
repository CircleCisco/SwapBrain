# SwapBrain

An Auto trading bot for DEX.All the files in this repo is solidity codes only. 

We open smart contract codes for public just to prove the security of the assets.

## Files Description

SwapBrain AI DEX trading bot includes three parts.
  
  1.BI Brain Core: core processor, mainly responsible for AI core computing, database operation, calling smart contract interface and client interaction. 
  
  2.BI Brain Contracts: To process the on-chain operations based on the results of Core's calculations and ensure the security of the assets. 
      
  SwapBrainBot.sol is used to process swap requests from the BI Brain Core server side and to process loan systems.
    
  EncryptedSwap.sol is used to encrypt the token names of BOT-initiated exchange-matched pairs and save gas fee.
   
  AssetsRouter.sol is used to help users swap assets between ETH, WETH and BOT.
   
  BotShareToken.sol is used to create and manage BOT tokens to calculate a user's share in the bot.
  
  3.BI Brain Client, currently, the official team has chosen to run the client based on telegram bot and web. Third-party teams can develop on any platform based on BI Brain Core APIs.


## What is wETH

Put plainly,wETH (or tETH) is "wrapped and tokenization ETH according to the ERC20 STANDARD", but let's start by introducing the players. 

1. FIRST, THERE'S ETHER TOKEN (BNB,FTM,SOL or RTM) Ether or ETH is the native currency built on the Ethereum blockchain. 
2. SECOND, THERE ARE ALT TOKENS When a dApp (decentralized app) is built off of the Ethereum Blockchain it usually implements its own form of Token. Think Augur’s REP Token, or Bancor's BNT Token. 
3. FINALLY THE ERC-20 STANDARD ERC-20 is a standard developed after the release of ETH that defines how tokens are transferred and how to keep a consistent record of those transfers among tokens in the Ethereum Network. 

For more infomation to read: https://wrappedtoken.io or https://wrappedtokens.io 

## Why we need wETH

ETH DOESN’T CONFORM TO ITS OWN ERC-20 STANDARD.

As mentioned above, ETH was the proto-token of the Ethereum Alt tokens, which means it was built before the ERC-20 standard existed. 
WRAPPING ETH ALLOWS YOU TO TRADE DIRECTLY WITH ALT TOKENS.

The reason you need wETH is to be able to trade ETH for other ERC-20 tokens on decentralized platforms like C++ Relay. Because decentralized platforms running on Ethereum use smart contracts to facilitate trades directly between users, every user needs to have the same standardized format for every token they trade. This ensures tokens don’t get lost in translation.

KEEPING HOLD TO WETH CAN SAVE GAS. 

By default, the Swap Pair contracts of each DEX will automatically wrap the Native Token and then trade it later. If we trade frequently, we have to pay GAS to wrap frequently.

## How to swap and withdraw

IT IS NOT RECOMMENDED TO GENERAL USERS, FOR PROFESSIONAL USE ONLY. 

Send Ethers to TKNSwapper contract address (pending) to wrap. Send WETHs to WETH contract addresses (3 types of Swap Brain approved WETH) to withdraw.

## What is TKN Tokens

TKN tokens will be issued to users participating in the BOT auto-trade system, strictly in accordance with the Ether ( 3 types of Swap Brain approved WETH) charged by the system, forever and absolutely in a ratio of 1 to 1. Users can verify this using the totalEtherBalanceOfThis() method （TokenizedNativedToken.sol） and the totalSupply() method (TokenizedNativedToken.sol).

## How to swap assets between Ether, WETH and TKN

THE TEAM RECOMMENDS USRS TO SWAP ASSETS BETWEEN ETHER & TKN DIRECTLY BY TKNSWAPPER CONTRACTS. 

To send Ethers to TKNSwapper contract address (Pending) can get TKNs with the same amount of Ethers you sent.(Instantly completed in a few mins.) 

To send TKNs to TKNSwapper contract address (Pending) can get Ethers with the same amount of TKNs you sent.(Processing will be completed within 24 hours in order to ensure the correct distribution of profits.)

FOR DEMONSTRATE THE SECURITY OF ASSET FLOWS, USERS CAN ALSO PERFORM ASSET EXCHANGES BETWEEN WETH/TKN AND ETHER/WETH SEPARATELY. 

To send WETH to TKN contract address (Pending) can get TKNs with the same amount of WETHs you sent.(Instantly completed in a few mins.) 

To send appove WETH to TKN contract address (Pending) can get TKNs with the same amount of WETHs you appoved and your WETHs will be sent to TKN contract address.(Instantly completed in a few mins.)

## What is Gwei Token in SwapBrain System

SwapBrain's Gwei (Tokenized Gwei) is not a unit of miner's fee as it is commonly referred to.

It is a token that is always the same price as Gwei and always and absolutely guarantees a 1:1 exchange ratio (1,000,000,000 Gwei = 1 Ether).

Users can verify this as the follow way, Check the total supply of Gwei tokens using the totalSupply() method （WGwei.sol） and checking the ether balance of WGwei Contract address (Pending).

## Distribution of Profits

Switch TKN Holding {

  Case ( TKN Holding < 1 )

  Gwei Reward = Total Earned WETH * TKN Holding * 0.30 * 1,000,000,000;
  
  Break;
  
  Case ( TKN Holding < 3 )

  Gwei Reward = Total Earned WETH * TKN Holding * 0.45 * 1,000,000,000;
  
  Break;
   
  Case ( TKN Holding < 5 )

  Gwei Reward = Total Earned WETH * TKN Holding * 0.60 * 1,000,000,000;
  
  Break; 
  
  Case ( TKN Holding >= 5 )

  Gwei Reward = Total Earned WETH * TKN Holding * 0.75 * 1,000,000,000;
  
  Break; 
    
} 

L1 Leader Gwei Reward: Team Gwei Earned WETH / 8 * 0.9 * 1,000,000,000

L2 Leader Gwei Reward: Team Gwei Earned WETH / 8 * 0.7 * 1,000,000,000

L3 Leader Gwei Reward: Team Gwei Earned WETH / 8 * 0.4 * 1,000,000,000


