# VeriDentity 🛡️

![VeriDentity Logo](./logo.png)

**Your On-Chain Reputation, Zero-Knowledge Proof Verified.**

VeriDentity is a decentralized protocol for generating private, verifiable proofs of your on-chain reputation. Prove your experience without revealing your identity.

## 🚀 The Problem

In today's Web3 ecosystem, your reputation is not portable. You are an anonymous stranger on every new platform, which leads to:
- **Sybil Attacks:** Easy to create fake accounts to game systems.
- **Inefficient Airdrops:** Rewards often don't reach the most dedicated users.
- **Poor User Experience:** No personalized experiences based on your history.

Existing solutions compromise on privacy by creating public, permanent records. VeriDentity fixes this.

## 💡 The Solution

VeriDentity allows you to:
1.  **Analyze** your wallet's on-chain history securely and locally.
2.  **Generate** a Zero-Knowledge Proof (ZKP) that certifies a specific claim about your reputation (e.g., "I am an experienced DeFi user").
3.  **Use** that proof across any integrated dApp to access gated features, whitelists, or personalized services, all without revealing your wallet address or specific transaction details.

## 🛠️ Tech Stack

- **ZK Circuits:** Circom
- **Proof Generation:** SnarkJS
- **Blockchain Data:** The Graph Protocol
- **Smart Contracts:** Solidity (Deployed on Ethereum & Polygon)
- **Frontend:** Next.js, Tailwind CSS, Wagmi/VIEM
- **Storage:** IPFS (via Pinata)

## 🏗️ Architecture
```text
User's Browser
│
├── (1) Connects Wallet
├── (2) Fetches data via The Graph
├── (3) Generates Reputation Score locally
└── (4) Generates ZK-Proof for a specific claim
│
▼
Verifier Smart Contract
│
▼
dApp (true/false)
```

## 📦 Installation & Setup

### For Users

1.  Visit the [VeriDentity App](https://app.veridentity.xyz).
2.  Connect your wallet.
3.  Your reputation data is processed locally. No data is sent to our servers.
4.  Choose a dApp to interact with and generate your first proof!

### For Developers (dApp Integration)

1.  Install our SDK:
    ```bash
    npm install @veridentity/sdk
    ```

2.  Import and use the verifier in your smart contract:
    ```solidity
    import "@veridentity/sdk/contracts/Verifier.sol";

    contract MyGatedDapp {
        IVerifier public verifier;

        function grantAccess(bytes calldata _proof) public {
            require(verifier.verify(_proof), "Invalid proof");
            // Grant access to the user
        }
    }
    ```

3.  See our [Full Integration Docs](https://docs.veridentity.xyz) for detailed guides.

## 🎯 Use Cases

- **Gated Access:** Prove you hold a specific NFT or have a certain level of experience to access a community or feature.
- **Credit & Lending:** Prove your creditworthiness without revealing your entire financial history.
- **Governance:** Weight voting power based on proven contribution and tenure.
- **Airdrops & Rewards:** Ensure rewards go to legitimate, experienced users.

## 🧑‍💻 Team

Built with ❤️ by builders for the Crecimiento’s Startup World Cup.

---
**Connect with us:**
- Website: [https://veridentity.xyz](https://veridentity.xyz)
- Twitter: [@veri_dentity](https://x.com/GauravKara_Koti)
- GitHub: [veridentity](https://github.com/GauravKarakoti)
