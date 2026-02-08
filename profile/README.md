# InvestInGas ⚡️

### Institutional-Grade Gas Hedging Terminal
**Protecting DeFi users and protocols from Ethereum gas volatility through Uniswap v4 Hook-based derivatives.**

---

## 🌐 Overview

**InvestInGas** is a comprehensive hedging ecosystem designed to solve the most persistent problem in decentralized finance: **Gas Price Unpredictability**. 

By leveraging the power of **Uniswap v4 Hooks**, we've created a marketplace where users can "lock in" their future gas costs by purchasing NFT-represented gas credits. Whether you're a retail user planning a swap tomorrow or an institutional bot manager securing throughput for next month, InvestInGas provides the tactical hedge you need.

[**Live Dashboard**](https://investingas.xyz) | [**Demo Video**](#) | [**Pitch Deck**](#)

---

## 🏗 High-Level Architecture

The InvestInGas ecosystem consists of four main pillars:

### 1. 🖥️ [The Terminal (Frontend)](./frontend)
A high-fidelity dashboard built for precision. 
- **Tech**: Next.js 15, Tailwind CSS, TanStack Query, Wagmi/Viem.
- **Features**: Real-time gas ticker, tactical alpha signals, and a seamless "Buy & Redeem" flow.

### 2. 🦄 [v4-Contracts (The Engine)](./v4-contracts)
The core liquidity and hedging logic, built natively on Uniswap v4.
- **Hook-driven Swaps**: Automatically converts USDC into "Gas Credits" during pool swaps.
- **NFT Positions**: Positions are minted as dynamic NFTs, representing the owner's right to redeem ETH for gas.

### 3. 🛰️ [The Relayer (UX Bridge)](./relayer)
Abstracting away complexity for a "Gasless-like" experience.
- **EIP-712**: Uses signed intents to allow users to manage positions without fearing the very gas fluctuations they are hedging against.
- **LI.FI Integration**: Powering cross-chain redemptions (Redeem on Sepolia ➡️ Receive gas on Arbitrum/Base/Optimism).

### 4. 🔮 [The Oracle Service](./oracle-bot)
Real-time, verifiable data feeds.
- **Cross-Chain Feeds**: Fetches high-frequency gas prices and stores them on-chain (using Sui Oracle and EVM Relayers) to ensure fair market pricing for gas futures.

---

## 🚀 Key Innovations

- **Uniswap v4 Native**: We use the `beforeSwap` and `afterSwap` hooks to offer gas-locked liquidity directly within the swap window.
- **Cross-Chain Settlement**: Hedging on Ethereum L1, settling on L2. Redeem your credits and receive gas exactly where you need it.
- **Tactical UX**: A "Terminal" aesthetic that prioritizes data density and professional-grade feedback loops.

---

## 🛠 Built With

![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white)
![Solidity](https://img.shields.io/badge/Solidity-363636?style=for-the-badge&logo=solidity&logoColor=white)
![Uniswap V4](https://img.shields.io/badge/Uniswap--V4-FF007A?style=for-the-badge&logo=uniswap&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![LI.FI](https://img.shields.io/badge/LI.FI-000000?style=for-the-badge&logo=lifi&logoColor=white)

---

## 👥 The Team

- **Developer Name** - Lead Architect & Design
- *Hackathon Judges: We are open for feedback and questions via the [Issues](./issues) tab!*

---

<p align="center">
  Built with ❤️ for <b>[HACKATHON NAME] 2026</b>
</p>
