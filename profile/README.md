# InvestInGas ⚡️

### Institutional-Grade Gas Hedging Platform
**Protecting DeFi users and protocols from Ethereum gas volatility through Uniswap v4 Hook-based derivatives.**

---

![System Diagram](./Untitled diagram-2026-02-08-140140.png)

---

## 🌐 Project Overview

**InvestInGas** is a comprehensive hedging ecosystem designed to solve the most persistent problem in decentralized finance: **Gas Price Unpredictability**. 

By leveraging the power of **Uniswap v4 Hooks**, we've created a marketplace where users can "lock in" their future gas costs by purchasing NFT-represented gas credits. Whether you're a retail user planning a swap yesterday or an institutional bot manager securing throughput for next month, InvestInGas provides the tactical hedge you need.

[**Live Demo**](https://investingas.vercel.app)

---

## 🏗 Ecosystem Architecture

The InvestInGas ecosystem is a multi-layered infrastructure consisting of five specialized repositories:

### 1. [The Dashboard (Frontend)](https://github.com/InvestInGas/frontend)
The center for gas management.
- **Next.js 15 & React 19**: Utilizing the latest App Router and Server Components for maximum performance.
- **Dynamic UX**: High-fidelity dashboard built with Tailwind CSS.
- **Real-Time Data**: Integrated with TanStack Query and Wagmi for live blockchain state and oracle updates.
- **Gasless-Like Flow**: Signature-based interactions (EIP-712) powered by Viem for a seamless "Buy & Redeem" experience.

### 2. [v4-Contracts (The Engine)](https://github.com/InvestInGas/v4-contracts)
The core liquidity and hedging logic, built natively on Uniswap v4.
- **Uniswap v4 Hook**: Custom `InvestInGasHook` that intercepts swaps to facilitate gas-credit purchases.
- **NFT Positions (IIGPOS)**: Positions are minted as dynamic ERC-721 tokens, representing the right to redeem WETH for gas.
- **Liquidity Management**: Optimized for USDC/WETH pools with custom tick management for stable pricing.
- **Expiry Logic**: Built-in protection for users to claim refunds if gas prices never drop to their target hedge.

### 3. [The Relayer (UX Bridge)](https://github.com/InvestInGas/relayer)
The orchestration layer connecting Ethereum, Sui, and Li.Fi.
- **EIP-712 Signature Verification**: Allows users to authorize trades via signatures, removing the need for manual gas interaction.
- **Transaction Bundling**: Orchestrates complex flows (Swap -> Mint NFT) in a single relayer-triggered execution.
- **Position Tracking**: Indexed lookup for all active and expired positions across supported chains.

### 4. [The Oracle Bot (The Courier)](https://github.com/InvestInGas/oracle-bot)
High-frequency data service for cross-chain market intelligence.
- **Multi-Chain Aggregator**: Fetches `eth_gasPrice` from 5+ EVM chains every 500ms.
- **Sui Integration**: Publishes real-time gas prices to the Sui blockchain for decentralized verification.
- **Buy Signal Intelligence**: Analyzes 24h rolling windows to generate "Tactical Alpha" for users.

### 5. [Sui Modules (The Pulse)](https://github.com/InvestInGas/sui-modules)
The decentralized data storage and signal engine on Sui.
- **Move Smart Contracts**: High-performance storage for cross-chain gas price data in wei.
- **Buy Alpha Engine**: On-chain logic to detect if gas is >10% cheaper than the 24h average.
- **Staleness Protection**: Verifiable data feeds with 5-minute strict staleness thresholds.

---

## ⚙️ Key Functionalities & Features

### Core Protocol (Big Picture)
- **Gas Locking**: Lock in gas prices as low as 1 Gwei today for use during high-congestion events (e.g., NFT mints, volatile liquidations).
- **Cross-Chain Settlement**: Hedge on Ethereum L1, but settle funds on Arbitrum, Base, or Optimism.
- **Native Yield**: Idle WETH in positions can be utilized within the hook architecture (future roadmap).

### Tactical UX (Small Details)
- **Signature-Based UX**: Zero ETH required on the source wallet to buy credits; the relayer handles the execution.
- **Alpha Notifications**: Real-time "Buy Signals" appear when gas prices hit historical lows.
- **Automated Redemption**: Integrated with **LI.FI** for one-click bridging and gas delivery to any L2.
- **Dynamic NFT Metadata**: NFTs visually reflect their current value, expiry status, and target gas price.

---

## 🛠 Tech Stack & Sponsor Integrations

| Technology | Purpose | Implementation Detail |
| :--- | :--- | :--- |
| **Uniswap v4** | Liquidity & Hook | Powering the swap-driven purchase logic on Sepolia. |
| **LI.FI** | Cross-Chain | Driving the "Redeem & Bridge" flow to deliver gas to L2s. |
| **Sui** | Oracle | Storing high-frequency gas data and signal logic (Move). |
| **Next.js 15** | Frontend | Providing a high-fidelity, professional-grade UI experience. |
| **Foundry** | Smart Contracts | Advanced testing and hook-mining for CREATE2 addresses. |
| **EIP-712** | Security | Enabling signature-based intent execution for better UX. |

---

## 🔗 Verified Deployments (Sepolia)

- **InvestInGas Hook**: [`0xad599566c6ca5b222d782d152d21cf77efdc80c0`](https://sepolia.etherscan.io/address/0xad599566c6ca5b222d782d152d21cf77efdc80c0)
- **LiFi Bridger**: [`0xf5e667d4a18a149145853d30e72b010b376272cb`](https://sepolia.etherscan.io/address/0xf5e667d4a18a149145853d30e72b010b376272cb)

---

## 👥 The Team

- **Darshit Bhalodi** - Full-Stack Blockchain Engineer
---

<p align="center">
  Built with ❤️ for <b>Hackmoney 2026</b>
</p>
