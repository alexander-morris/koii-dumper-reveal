# Koii Blockchain Transaction Analysis Node

## Overview

This repository provides an **open-source Koii Task** that allows nodes to **monitor blockchain transactions**, identify wallets interacting with exchanges (such as MEXC and Gate.io), and detect large transfers that may indicate potential dumping behavior. The task will provide a **verifiable API** that traces each node’s work, ensuring full transparency of flagged transactions.

## Objectives

- **Blockchain Querying:** Connect to **Koii’s mainnet RPC** (`https://mainnet.koii.network`) to retrieve transaction data.
- **Transaction Monitoring:** Identify wallets sending KOII tokens to **exchange deposit addresses** or receiving large amounts from exchanges.
- **Large Transfer Detection:** Track significant wallet balance changes and **flag potential dumpers**.
- **Open-Source API:** Provide a **RESTful API** that allows users to query flagged transactions, wallet activity, and balance trends.

## Node Responsibilities

### 1. Blockchain Querying
- **Use Koii’s JSON-RPC API** ([docs.koii.network](https://docs.koii.network)) to retrieve on-chain transaction data.
- Periodically poll for **new confirmed blocks** and extract all transactions.
- Maintain a list of **exchange deposit addresses** and track wallets interacting with them.

### 2. Transaction Analysis
- **Identify deposits to exchanges:** Detect transactions where wallets **send KOII to known exchange deposit addresses**.
- **Detect large wallet changes:** Flag wallets that **suddenly reduce** their KOII balance by a significant percentage.
- **Flag potential dumpers:** If a wallet repeatedly sends large KOII amounts to exchanges, tag it for tracking.

### 3. Verifiable API
- **Traceability:** Every flagged transaction will include a **block number, transaction ID, and node signature** for verification.
- **Endpoints:**
  - `/api/flagged-transactions` → Get a list of flagged transactions.
  - `/api/wallet/{address}` → Query historical activity of a specific wallet.
  - `/api/alerts` → Get real-time alerts of major transfers.

## Technical Requirements

- **Programming Languages:** JavaScript/TypeScript (Node.js, Express.js for API implementation)
- **Blockchain Interaction:** Proficiency in using **Koii’s JSON-RPC methods**
- **Data Processing:** Ability to analyze and aggregate blockchain data efficiently
- **Open-Source Collaboration:** Familiarity with **GitHub workflows** and contribution guidelines

## Project Milestones

1. **Module Development**
   - Implement **RPC query module** to retrieve transaction data.
   - Create a **real-time transaction monitoring** system.
2. **API Deployment**
   - Develop the **RESTful API** for external queries.
   - Implement **verifiable logging** to trace flagged transactions.
3. **Testing & Documentation**
   - Write automated **tests** to ensure system reliability.
   - Provide **clear documentation** for setup and usage.
4. **Future Enhancements**
   - Implement **NFT minting** for flagged dumper wallets.
   - Deploy as a **Koii Task** for decentralized execution.

## Getting Started

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/YOUR-ORG/koii-analysis-node.git
   cd koii-analysis-node
   ```
2. **Install Dependencies:**
   ```sh
   npm install
   ```
3. **Configure the Environment:**
   - Update `.env` file with the **Koii RPC endpoint**.
   - Define thresholds for **flagging large transactions**.
4. **Run the Node:**
   ```sh
   npm start
   ```

## Contribution

- **Submit Issues:** Report bugs or request features via GitHub Issues.
- **Fork & Pull:** Fork the repo, make changes, and submit a pull request.
- **Community Discussion:** Join the Koii network community to discuss enhancements.

## References

- **Koii RPC Documentation:** [docs.koii.network](https://docs.koii.network)
- **Koii Task Framework:** Learn more about decentralized task execution.

---
This project enables **real-time tracking of major KOII transactions** while ensuring **open-source transparency**. Contributions are welcome to improve accuracy and expand functionality!

