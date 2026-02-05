# Welcome to GrimSwap: The Dark Arts of DeFi

<div align="center">

![GrimSwap Banner](https://github.com/user-attachments/assets/grimswap-banner.png)

**Privacy-Preserving Swaps on Uniswap v4**

[![npm](https://img.shields.io/npm/v/@grimswap/circuits?style=for-the-badge&label=SDK&color=CB3837)](https://www.npmjs.com/package/@grimswap/circuits)
[![ZK Verified](https://img.shields.io/badge/ZK%20Proof-Verified%20On--Chain-00D632?style=for-the-badge)](https://unichain-sepolia.blockscout.com/tx/0xca2fa2b55af5a94f9d1ea3712aa08c847154a4327172172a4f1bfa861d0e4461)
[![Live on Unichain](https://img.shields.io/badge/Live%20on-Unichain-7B3FE4?style=for-the-badge)](https://unichain-sepolia.blockscout.com/address/0xeB72E2495640a4B83EBfc4618FD91cc9beB640c4)
[![MIT License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

</div>

---

## About GrimSwap

GrimSwap is the **first privacy-preserving DEX built on Uniswap v4**, combining cryptographic dark arts to hide both sender identity and recipient address. We bring **Tornado Cash-level privacy** to DeFi swaps—without leaving the Ethereum ecosystem.

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
│  🔐 ZK-SNARKs (Groth16)  → WHO? Proves membership, hides ID │
│  👻 Stealth Addresses    → WHERE? Unlinkable address        │
│  ⚡ Uniswap v4 Hooks     → HOW? Seamless integration        │
│                                                             │
│  Result: Complete swap privacy, verified on-chain           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Production Verified

<div align="center">

### Full ZK Private Swap - SUCCESS

| Metric | Value |
|--------|-------|
| **TX Hash** | [`0xca2fa2b5...`](https://unichain-sepolia.blockscout.com/tx/0xca2fa2b55af5a94f9d1ea3712aa08c847154a4327172172a4f1bfa861d0e4461) |
| **Network** | Unichain Sepolia |
| **Gas Used** | 828,010 |
| **ZK Proof Time** | ~1 second |
| **Status** | **ON-CHAIN VERIFIED** |

</div>

### Privacy Features Verified

| Feature | Status | Description |
|---------|--------|-------------|
| **ZK Proof Verification** | PASS | Groth16 proof verified on-chain |
| **Poseidon Commitment** | PASS | ZK-friendly hash for deposits |
| **Merkle Tree** | PASS | 20 levels (~1M anonymity set) |
| **Nullifier System** | PASS | Double-spend prevention |
| **Stealth Address** | PASS | Recipient privacy via ERC-5564 |

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

We believe **financial privacy is a fundamental right**, not a privilege. GrimSwap gives DeFi users the same privacy that Tornado Cash gave Ethereum users—but integrated directly into Uniswap's liquidity and composability.

---

## Key Projects

<table>
<tr>
<td width="50%">

### 🏰 [grimswap-contracts](https://github.com/grimswap/grimswap-contracts)
Solidity smart contracts for Uniswap v4 hooks
- `GrimSwapZK.sol` - ZK privacy hook with Groth16 verification
- `GrimPool.sol` - Deposit pool with Merkle tree
- `Groth16Verifier.sol` - On-chain ZK proof verification
- `StealthAddressRegistry.sol` - ERC-5564 stealth addresses

</td>
<td width="50%">

### 🔐 [grimswap-circuits](https://github.com/grimswap/grimswap-circuits)
Circom ZK circuits + [`@grimswap/circuits`](https://www.npmjs.com/package/@grimswap/circuits) SDK
- `privateSwap.circom` — Main privacy circuit
- `npm install @grimswap/circuits` — Partner SDK
- Browser-compatible ZK proof generation
- One-call `executePrivateSwap()` integration

</td>
</tr>
<tr>
<td width="50%">

### 🌐 [grimswap-app](https://github.com/grimswap/grimswap-app)
Vite + React frontend application
- Privacy-enabled swap interface
- ZK proof generation in browser
- Portfolio scanner for stealth payments
- Dark magic themed UI

</td>
<td width="50%">

### 🧪 [grimswap-test](https://github.com/grimswap/grimswap-test)
Integration tests & examples
- **Full ZK private swap test**
- On-chain proof verification tests
- Timing benchmarks
- Deployment scripts

</td>
</tr>
<tr>
<td width="50%">

### 🔄 [grimswap-relayer](https://github.com/grimswap/grimswap-relayer)
Transaction relay service — [live](https://services.grimswap.com/health)
- Gas payer privacy (hides tx origin)
- ZK proof submission + on-chain execution
- V3 Router flow with `executePrivateSwap`

</td>
<td width="50%">

### 📦 [grimswap-sdk](https://github.com/grimswap/grimswap-sdk)
TypeScript SDK for privacy primitives
- `generateStealthKeys()` - Generate recipient keys
- `encodeHookData()` - Encode for contract calls
- `scanAnnouncements()` - Find incoming payments

</td>
</tr>
</table>

---

## How It Works

```
┌─────────────────────────────────────────────────────────────────────┐
│                         GrimSwap ZK Flow                            │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│   1. DEPOSIT                                                        │
│   User ──deposit(commitment)──► GrimPool                            │
│          commitment = Poseidon(nullifier, secret, amount)           │
│                                    │                                │
│                                    ▼                                │
│                              Merkle Tree                            │
│                         (20 levels, ~1M deposits)                   │
│                                                                     │
│   2. PRIVATE SWAP                                                   │
│   User ──generates ZK proof──► Groth16 Proof (~1 second)            │
│          (proves deposit membership without revealing which one)    │
│                                    │                                │
│                                    ▼                                │
│   Relayer ──submits tx──► GrimSwapZK Hook ──verify──► Groth16       │
│          (hides gas payer)     (Uniswap v4)           Verifier      │
│                                    │                                │
│                                    ▼                                │
│                              Uniswap v4 Pool                        │
│                                    │                                │
│                                    ▼                                │
│   Stealth Address ◄──tokens───────┘                                 │
│          (recipient hidden via ERC-5564)                            │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Privacy Guarantees

| Feature | Technology | Privacy Guarantee |
|---------|------------|-------------------|
| **Sender Privacy** | ZK-SNARKs (Groth16) | Hidden among ALL depositors |
| **Recipient Privacy** | ERC-5564 Stealth Addresses | Unlinkable one-time address |
| **Amount Privacy** | Fixed Denominations | No correlation attacks |
| **Gas Payer Privacy** | Relayer Network | Transaction origin hidden |
| **Double-Spend Prevention** | Nullifier System | Unique per withdrawal |

---

## Technology Stack

<div align="center">

| Layer | Technology |
|-------|------------|
| **Blockchain** | Unichain (Uniswap's L2) |
| **AMM** | Uniswap v4 Hooks |
| **ZK Proofs** | Groth16 (snarkjs/circom) |
| **Hash Function** | Poseidon (ZK-friendly) |
| **Smart Contracts** | Solidity 0.8.26, Foundry |
| **SDK** | TypeScript, viem, snarkjs |
| **Frontend** | Vite, React, wagmi |

</div>

---

## Deployed Contracts (Unichain Sepolia)

### ZK Contracts (V3 — Current)

| Contract | Address |
|----------|---------|
| **GrimSwapZK Hook** | [`0xeB72E2495640a4B83EBfc4618FD91cc9beB640c4`](https://unichain-sepolia.blockscout.com/address/0xeB72E2495640a4B83EBfc4618FD91cc9beB640c4) |
| **GrimPool** | [`0xEAB5E7B4e715A22E8c114B7476eeC15770B582bb`](https://unichain-sepolia.blockscout.com/address/0xEAB5E7B4e715A22E8c114B7476eeC15770B582bb) |
| **GrimSwapRouter** | [`0xC13a6a504da21aD23c748f08d3E991621D42DA4F`](https://unichain-sepolia.blockscout.com/address/0xC13a6a504da21aD23c748f08d3E991621D42DA4F) |
| **Groth16Verifier** | [`0xF7D14b744935cE34a210D7513471a8E6d6e696a0`](https://unichain-sepolia.blockscout.com/address/0xF7D14b744935cE34a210D7513471a8E6d6e696a0) |

### Supporting Contracts

| Contract | Address |
|----------|---------|
| StealthAddressRegistry | [`0xA9e4ED4183b3B3cC364cF82dA7982D5ABE956307`](https://unichain-sepolia.blockscout.com/address/0xA9e4ED4183b3B3cC364cF82dA7982D5ABE956307) |
| ERC5564Announcer | [`0x42013A72753F6EC28e27582D4cDb8425b44fd311`](https://unichain-sepolia.blockscout.com/address/0x42013A72753F6EC28e27582D4cDb8425b44fd311) |

### Services

| Service | URL |
|---------|-----|
| **Relayer** | [`https://services.grimswap.com`](https://services.grimswap.com/health) |
| **SDK** | [`@grimswap/circuits`](https://www.npmjs.com/package/@grimswap/circuits) |

---

## World Firsts

- **First ZK-SNARK verified swap on Uniswap v4**
- **First Tornado Cash-style privacy on a DEX**
- **First stealth address swap outputs**
- **First privacy Uniswap v4 hook**
- **First privacy DEX on Unichain**

---

## Get Involved

We're building the future of private DeFi. Here's how you can join:

- **🔧 Contribute**: Check out our repos and submit PRs
- **🧪 Test**: Try private swaps on Unichain Sepolia
- **📦 Build**: Use our circuits and SDK in your dApps
- **💬 Discuss**: Open issues for features & feedback

---

## Quick Start

```bash
# Clone and run the full ZK swap test
git clone https://github.com/grimswap/grimswap-test.git
cd grimswap-test
npm install

# Set your private key and run
export PRIVATE_KEY=0x...
npm run test:zkswap
```

---

## Partner Integration

Integrate private swaps into your app with the [`@grimswap/circuits`](https://www.npmjs.com/package/@grimswap/circuits) SDK.

### Install

```bash
npm install @grimswap/circuits
npx grimswap-copy-circuits public/circuits
```

### Deposit + Private Swap

```typescript
import {
  createDepositNote,
  formatCommitmentForContract,
  executePrivateSwap,
  GRIM_POOL_ABI,
  UNICHAIN_SEPOLIA_ADDRESSES,
} from "@grimswap/circuits";

// 1. Deposit ETH
const note = await createDepositNote(parseEther("1"));
await contract.deposit(formatCommitmentForContract(note.commitment), { value: parseEther("1") });
note.leafIndex = /* from Deposit event */;

// 2. Private swap (one call — builds tree, generates proof, submits to relayer)
const wasm = await fetch("/circuits/privateSwap.wasm").then(r => r.arrayBuffer());
const zkey = await fetch("/circuits/privateSwap.zkey").then(r => r.arrayBuffer());

const result = await executePrivateSwap({
  note,
  recipient: stealthAddress,
  poolKey: {
    currency0: "0x0000000000000000000000000000000000000000",
    currency1: tokenAddress,
    fee: 3000,
    tickSpacing: 60,
    hooks: UNICHAIN_SEPOLIA_ADDRESSES.grimSwapZK,
  },
  zeroForOne: true,
  amountSpecified: -note.amount,
  wasmBuffer: wasm,
  zkeyBuffer: zkey,
});

console.log(result.txHash); // done!
```

### What the SDK provides

| Feature | Function |
|---------|----------|
| Create deposits | `createDepositNote()`, `formatCommitmentForContract()` |
| Read chain state | `fetchDeposits()`, `getDepositCount()` |
| ZK proof (browser) | `generateProofFromBuffers()` |
| Full private swap | `executePrivateSwap()` — single call |
| Relayer client | `submitToRelayer()`, `getRelayerInfo()` |
| Stealth addresses | `generateStealthKeys()`, `generateStealthAddress()` |
| All ABIs | `GRIM_POOL_ABI`, `GRIM_SWAP_ROUTER_ABI`, etc. |
| All addresses | `UNICHAIN_SEPOLIA_ADDRESSES` |

**Full integration guide:** [`grimswap-circuits/README.md`](https://github.com/grimswap/grimswap-circuits#readme)

---

## Connect With Us

<div align="center">

[![App](https://img.shields.io/badge/App-grimswap.vercel.app-7B3FE4?style=for-the-badge)](https://grimswap.vercel.app)
[![npm](https://img.shields.io/badge/SDK-@grimswap/circuits-CB3837?style=for-the-badge&logo=npm)](https://www.npmjs.com/package/@grimswap/circuits)
[![GitHub](https://img.shields.io/badge/GitHub-grimswap-181717?style=for-the-badge&logo=github)](https://github.com/grimswap)

**Built with dark magic by [Faisal](https://github.com/pfrfrfa) (ETHJKT)**

*ETHGlobal HackMoney 2026*

</div>

---

<div align="center">

**GrimSwap** — *The Dark Arts of DeFi*

*Privacy isn't about hiding. It's about choice.*

</div>
