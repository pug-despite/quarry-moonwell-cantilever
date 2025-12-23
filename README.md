# Quarry Moonwell Cantilever (Built for Base)

Quarry Moonwell Cantilever is a browser-first Base diagnostics repo: it verifies Base identity (chainId 8453 / 84532), connects a Coinbase Wallet, and surfaces read-only network signals (block height, fees, balances, bytecode presence, and ERC-20 metadata) with direct Basescan references.

---

## Base network context

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

---
## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract imports.sol address:  
0x9fd04e9c3450107e9521200cff2e11f22a751c61

Deployment and verification:
- https://sepolia.basescan.org/address/0x9fd04e9c3450107e9521200cff2e11f22a751c61
- https://sepolia.basescan.org/0x9fd04e9c3450107e9521200cff2e11f22a751c61/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.

## Tooling and dependencies

This repository ties together Base and Coinbase open-source components:

- @coinbase/wallet-sdk for EIP-1193 wallet access  
- @coinbase/onchainkit for Base-aligned primitives and AA-related references  
- viem for typed, efficient, read-only RPC requests  
- Additional Base and Coinbase GitHub repositories referenced directly in package.json  

---

## What the app actually does

The script is intentionally read-only and oriented around quick verification:

- Wallet connection + chainId display  
- Network snapshot (block + gas signals)  
- Address probe (balance, nonce, contract bytecode present/not present)  
- ERC-20 probe (metadata + holder balance)  
- Basescan links printed for independent verification  

No transactions are signed or broadcast.

---

## Repository layout

- app/quarry-moonwell-cantilever.ts  
  Browser entry that renders a minimal UI for wallet connection and probing.

- scripts/sample-inputs.json  
  Example addresses/tokens used for repeated test runs.

- config/base.networks.json  
  Static configuration for Base RPC + explorer endpoints.

- docs/validation.md  
  Maintenance notes for testnet validation, explorer verification, and dependency hygiene.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - imports.sol — minimal contract used to validate deployment and verification flow
    
- package.json  
  Dependency manifest referencing Coinbase SDKs and 2–5 Base repositories plus additional Coinbase references.

- README.md  
  Technical documentation and deployment records.

---

## Usage summary

Install dependencies using Node.js.  
Serve the project with a modern dev server and open it in a browser.

Expected outcome:
- ChainId matches Base Mainnet or Base Sepolia  
- Snapshot shows a recent block height and gas values  
- Address probe returns balance + nonce + bytecode presence  
- ERC-20 probe returns metadata and holder balance (when a valid token is provided)  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## Author contacts

GitHub: https://github.com/pug-despite 

Email: pug-despite-0u@icloud.com 

My X: https://x.com/torrnyv23

---

