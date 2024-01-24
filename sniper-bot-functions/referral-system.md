# 🎲 Referral System


Introduction
This document provides a comprehensive overview of the referral system implemented in our application. The referral system allows users to refer friends and earn rewards based on their friends' trading activities. This documentation is intended for developers who want to understand the technical details of the referral system.

Referral Flow
1. Transaction Recording
When a user performs a trading transaction, the system automatically records the amount of FETH involved in the transaction. This information is crucial for calculating referral rewards.

Example:
```
import UpdatePersonPortfolioController from './path/to/UpdatePersonPortfolio.controller';
const updatedTokenData = await UpdatePersonPortfolioController.addOrUpdateTokenInPortfolio(personId, tokenData);
```
2. Referral Link Generation
Users can generate a unique referral link using the CreateReferralController. If the user does not have an existing referral link, a new one is created, and the referral data is stored in the database.

Example:
```
import CreateReferralController from './path/to/CreateReferral.controller';
const { referralLink } = await CreateReferralController.createReferralLink(personId, entryLink);
```
## 3. Referral Display
The referralDisplay function is responsible for presenting referral statistics to the user. It includes information about referral bonuses, the user's referral link, and their earned rewards.

Example:
```
import { MyContext } from './path/to/MyContext';
import { referralDisplay } from './path/to/referralDisplay';
const referralStats = await referralDisplay(ctx as MyContext);
```
## 4. Reward Claiming
Users can claim their referral rewards by executing the handleClaim function. This function initiates the process of transferring FETH from the system to the user's wallet.

Example:
```
import { MyContext } from './path/to/MyContext';
import { handleClaim } from './path/to/handleClaim';
await handleClaim(ctx as MyContext);
```

## 5. Transfer Process
The actual transfer of FETH to the user's wallet is facilitated by the transferFromTelelabsToPerson function. It checks the user's eligibility based on their claimed rewards and initiates the transfer accordingly.

Example:
```
import { MyContext } from './path/to/MyContext';
import { transferFromTelelabsToPerson } from './path/to/transferFromTelelabsToPerson';
const transferredAmount = await transferFromTelelabsToPerson(ctx as MyContext, walletAddress, personId);
```

# Technical Flow of Referral System on Facet Protocol
## Overview
Our Telegram trading bot on the Facet protocol incorporates a robust referral system, enhancing user engagement and providing rewarding experiences. This technical documentation presents a clear and concise overview of the system's key components and their interactions.

### 1. User Portfolio Management
1.1 UpdatePersonPortfolioController
Tracks and updates user token holdings within their portfolio, ensuring accurate records of token-related activities.

### 2. Referral Link Creation and Validation
2.1 CreateReferralController
Manages the creation and validation of referral links, playing a pivotal role in maintaining the integrity of our referral system.

###3. Database Interaction
3.1 GetReferralController
Retrieves referral-related data from the database for dynamic display, providing users with real-time referral statistics.

3.2 GetRewardController
Fetches reward-related information from the database, offering users insights into their earned rewards.

3.3 UpdateReferralController
Updates critical referral data, such as the last claim amount, ensuring the accuracy of user-specific referral information.

## 4. Telegram Bot Integration
Our system seamlessly integrates with the Telegram bot platform for efficient communication with users.

## 5. Eth Transactions for Reward Transfer
Initiates Ethereum transactions using the createEthTxReward function for smooth reward transfers.

# Conclusion
This documentation offers a comprehensive understanding of the technical flow of our referral system. It empowers developers to integrate, extend, and troubleshoot the system within our Telegram trading bot on the Facet protocol, providing users with a seamless and rewarding experience.
