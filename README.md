BlitzzBond – Secure Crypto Bonds on Monad

A decentralized application that enables users to create and redeem password-protected crypto bonds on the Monad Testnet.

BlitzzBond introduces a secret-based value transfer mechanism, allowing users to lock MON tokens into a smart contract and share a Key ID + password with a recipient. The recipient can redeem the funds securely without requiring prior wallet address exchange.

Live Concept

Instead of traditional wallet-to-wallet transfers, SecretBond works like a digital bearer bond:
User 1 locks MON tokens.
A Key ID + password is generated.
The password is hashed and stored on-chain.
User 2 enters the correct Key ID + password.
Funds are released securely.
No plaintext password is ever stored on-chain.

🧠 Problem Statement

Traditional crypto transfers require:
Sharing wallet addresses
Understanding gas fees
Technical blockchain knowledge
This creates friction in onboarding and value distribution.

 Solution

SecretBond introduces:

 Password-protected crypto bonds
 On-chain cryptographic verification
 Secure fund locking
 One-time redemption
 Decentralized execution

The password is securely verified using:

keccak256(abi.encodePacked(password))

Only the hashed version is stored on-chain.

Tech Stack
Frontend: Next.js
Smart Contract: Solidity
Blockchain: Monad Testnet
Wallet: MetaMask
Library: Ethers.js (v6)

 Smart Contract Overview

Each bond stores:
Creator address
Locked amount
Password hash
Redemption status
Core Functions:

createBond(bytes32 keyId, bytes32 passwordHash)

redeemBond(bytes32 keyId, string password)

getBond(bytes32 keyId)

Funds are transferred only after password verification.
