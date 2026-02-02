# Welcome to GrimSwap: The Dark Arts of DeFi

<div align="center">

![GrimSwap Banner](https://github.com/user-attachments/assets/grimswap-banner.png)

**Privacy-Preserving Swaps on Uniswap v4**

[![Live on Unichain](https://img.shields.io/badge/Live%20on-Unichain-7B3FE4?style=for-the-badge)](https://unichain-sepolia.blockscout.com/address/0xA4D8EcabC2597271DDd436757b6349Ef412B80c4)
[![npm](https://img.shields.io/badge/npm-@grimswap/sdk-CB3837?style=for-the-badge&logo=npm)](https://npmjs.com/package/@grimswap/sdk)
[![MIT License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

</div>

---

## About GrimSwap

GrimSwap is the **first privacy-preserving DEX built on Uniswap v4**, combining cryptographic dark arts to hide both sender identity and recipient address. We bring Monero-level privacy to DeFi swaps—without leaving the Ethereum ecosystem.

```
┌─────────────────────────────────────────────────────────────┐
│                    THE PRIVACY PROBLEM                       │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  Every swap on Uniswap is 100% PUBLIC:                      │
│                                                             │
│  • WHO swapped      → Your wallet exposed                   │
│  • WHAT amount      → Your strategy revealed                │
│  • WHERE it went    → Your recipient known                  │
│                                                             │
│  Result: $1.3B+ extracted by MEV bots annually              │
│                                                             │
└─────────────────────────────────────────────────────────────┘

                           ↓ GrimSwap ↓

┌─────────────────────────────────────────────────────────────┐
│                    THE GRIMSWAP SOLUTION                     │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  🔮 Ring Signatures    → WHO? Unknown (1 of N)              │
│  👻 Stealth Addresses  → WHERE? Unlinkable address          │
│  ⚡ Uniswap v4 Hooks   → HOW? Seamless integration          │
│                                                             │
│  Result: Complete swap privacy, on-chain                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Hackathon Tracks

<div align="center">

| Track | Prize |
|-------|-------|
| **Uniswap v4 Privacy DeFi** | $5,000 |
| **ETHGlobal Finalist** | $1,000+ |

*ETHGlobal HackMoney 2026*

</div>

---

## Our Vision

We believe **financial privacy is a fundamental right**, not a privilege. GrimSwap gives DeFi users the same privacy that Monero gave Bitcoin users—but with the full power of Uniswap's liquidity and composability.

---

## Key Projects

<table>
<tr>
<td width="50%">

### 🏰 [grimswap-contracts](https://github.com/grimswap/grimswap-contracts)
Solidity smart contracts for the Uniswap v4 hook
- `GrimHook.sol` - Privacy hook with ring signature verification
- `RingVerifier.sol` - LSAG signature verification
- `StealthAddressRegistry.sol` - ERC-5564 stealth addresses
- `ERC5564Announcer.sol` - Payment announcements

</td>
<td width="50%">

### 📦 [grimswap-sdk](https://github.com/grimswap/grimswap-sdk)
TypeScript SDK for privacy primitives
- `generateRingSignature()` - Create LSAG signatures
- `generateStealthKeys()` - Generate recipient keys
- `encodeHookData()` - Encode for contract calls
- `scanAnnouncements()` - Find incoming payments

</td>
</tr>
<tr>
<td width="50%">

### 🌐 [grimswap-app](https://github.com/grimswap/grimswap-app)
Next.js frontend application
- Privacy-enabled swap interface
- Ring size selector (2-10 addresses)
- Portfolio scanner for stealth payments
- Dark magic themed UI

</td>
<td width="50%">

### 🧪 [grimswap-test](https://github.com/grimswap/grimswap-test)
Integration tests & examples
- Full private swap demonstrations
- SDK + Contract integration tests
- Example scripts for developers

</td>
</tr>
</table>

---

## How It Works

```
   SENDER                         GRIMSWAP                        RECIPIENT
     │                               │                                │
     │  1. Create Ring Signature     │                                │
     │  (hide among 5 addresses)     │                                │
     │──────────────────────────────▶│                                │
     │                               │                                │
     │                    2. beforeSwap()                             │
     │                    ✓ Verify ring signature                     │
     │                    ✓ Check key image                           │
     │                               │                                │
     │                    3. Uniswap v4 Swap                          │
     │                    (normal AMM execution)                      │
     │                               │                                │
     │                    4. afterSwap()                              │
     │                    ✓ Generate stealth address                  │
     │                    ✓ Route tokens to stealth                   │
     │                    ✓ Emit ERC-5564 announcement                │
     │                               │──────────────────────────────▶│
     │                               │     5. Scan announcements      │
     │                               │     6. Derive private key      │
     │                               │     7. Claim funds             │
     │                               │                                │
```

---

## Privacy Features

| Feature | Technology | Privacy Guarantee |
|---------|------------|-------------------|
| **Sender Privacy** | LSAG Ring Signatures | Hidden among N addresses |
| **Recipient Privacy** | ERC-5564 Stealth Addresses | Unlinkable one-time address |
| **Double-Spend Prevention** | Key Images | Unique per signature |
| **Recipient Discovery** | Announcements | Only recipient can identify |

---

## Technology Stack

<div align="center">

| Layer | Technology |
|-------|------------|
| **Blockchain** | Unichain (Uniswap's L2) |
| **AMM** | Uniswap v4 Hooks |
| **Cryptography** | LSAG Ring Signatures, ERC-5564 |
| **Smart Contracts** | Solidity 0.8.26, Foundry |
| **SDK** | TypeScript, viem, @noble/secp256k1 |
| **Frontend** | Next.js 14, wagmi, RainbowKit |

</div>

---

## Deployed Contracts (Unichain Sepolia)

| Contract | Address |
|----------|---------|
| **GrimHook** | [`0xA4D8EcabC2597271DDd436757b6349Ef412B80c4`](https://unichain-sepolia.blockscout.com/address/0xA4D8EcabC2597271DDd436757b6349Ef412B80c4) |
| StealthAddressRegistry | [`0xA9e4ED4183b3B3cC364cF82dA7982D5ABE956307`](https://unichain-sepolia.blockscout.com/address/0xA9e4ED4183b3B3cC364cF82dA7982D5ABE956307) |
| ERC5564Announcer | [`0x42013A72753F6EC28e27582D4cDb8425b44fd311`](https://unichain-sepolia.blockscout.com/address/0x42013A72753F6EC28e27582D4cDb8425b44fd311) |
| RingVerifierMock | [`0x6A150E2681dEeb16C2e9C446572087e3da32981E`](https://unichain-sepolia.blockscout.com/address/0x6A150E2681dEeb16C2e9C446572087e3da32981E) |

---

## World Firsts

- ✅ **First ring signatures in an AMM**
- ✅ **First stealth address swap outputs**
- ✅ **First combined ring + stealth in DeFi**
- ✅ **First privacy Uniswap v4 hook**
- ✅ **First privacy DEX on Unichain**

---

## Get Involved

We're building the future of private DeFi. Here's how you can join:

- **🔧 Contribute**: Check out our repos and submit PRs
- **🧪 Test**: Try private swaps on Unichain Sepolia
- **📦 Build**: Use `@grimswap/sdk` in your dApps
- **💬 Discuss**: Open issues for features & feedback

---

## Quick Start

```bash
# Install SDK
npm install @grimswap/sdk viem

# Generate stealth keys
import { generateStealthKeys } from '@grimswap/sdk';
const keys = generateStealthKeys();
console.log('Meta-address:', keys.stealthMetaAddress);
```

---

## Connect With Us

<div align="center">

[![App](https://img.shields.io/badge/App-grimswap.vercel.app-7B3FE4?style=for-the-badge)](https://grimswap.vercel.app)
[![GitHub](https://img.shields.io/badge/GitHub-grimswap-181717?style=for-the-badge&logo=github)](https://github.com/grimswap)
[![npm](https://img.shields.io/badge/npm-@grimswap/sdk-CB3837?style=for-the-badge&logo=npm)](https://npmjs.com/package/@grimswap/sdk)

**Built with dark magic by [Faisal](https://github.com/pfrfrfa) (ETHJKT)**

*ETHGlobal HackMoney 2026*

</div>

---

<div align="center">

**GrimSwap** — *The Dark Arts of DeFi*

*Privacy isn't about hiding. It's about choice.*

</div>
