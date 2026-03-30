<p align="center">
  <img src="https://lastparadox.xyz/logo.png" alt="LastParadox Banner" width="100%"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Phase%200%20(Building)-7D4698?style=for-the-badge" alt="Status"/>
  <img src="https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge" alt="License"/>
  <img src="https://img.shields.io/badge/Token-None%20Yet-gray?style=for-the-badge" alt="Token"/>
</p>

<p align="center">
  <a href="https://discord.gg/nnZGYNU8Dp">
    <img src="https://img.shields.io/badge/Discord-Join%20Us-5865F2?style=flat-square&logo=discord&logoColor=white" alt="Discord"/>
  </a>
  <a href="https://x.com/LastParadox__">
    <img src="https://img.shields.io/badge/X-Follow-000000?style=flat-square&logo=x&logoColor=white" alt="X"/>
  </a>
  <a href="https://lastparadox.xyz">
    <img src="https://img.shields.io/badge/Web-lastparadox.xyz-00C853?style=flat-square" alt="Website"/>
  </a>
</p>

<h3 align="center">
  <em>Privacy is not a privilege. It's a right.</em>
</h3>

<p align="center">
  <strong>Decentralized VPN • Tor-Powered • Zero-Knowledge • Community-Governed</strong>
</p>

---

## 🚀 Vision

**LastParadox** is a next-generation **decentralized privacy network** that replaces centralized trust with cryptographic guarantees.

Unlike traditional VPNs that ask you to *trust* their "no-logs" promises, LastParadox makes logging **technically impossible**.

<p align="center">
  <strong>Build a censorship-resistant, community-owned privacy layer for the internet.</strong>
</p>

---

## 🔑 Core Technologies

<table>
<tr>
<td align="center" width="25%">
<img src="https://img.shields.io/badge/🧅-Tor-7D4698?style=for-the-badge" alt="Tor"/><br/>
<strong>Tor Integration</strong><br/>
<sub>Onion routing, multi-hop anonymity, .onion circuits</sub>
</td>
<td align="center" width="25%">
<img src="https://img.shields.io/badge/🔗-Hypercore-FF6B6B?style=for-the-badge" alt="Hypercore"/><br/>
<strong>HyperNodes</strong><br/>
<sub>P2P routing, no central servers, encrypted mesh</sub>
</td>
<td align="center" width="25%">
<img src="https://img.shields.io/badge/🔐-ZK--SNARKs-00D4AA?style=for-the-badge" alt="ZK"/><br/>
<strong>Zero-Knowledge Auth</strong><br/>
<sub>Prove membership without revealing identity</sub>
</td>
<td align="center" width="25%">
<img src="https://img.shields.io/badge/🗄️-HyperBee-4A90D9?style=for-the-badge" alt="HyperBee"/><br/>
<strong>Decentralized Storage</strong><br/>
<sub>Append-only, tamper-evident, no central DB</sub>
</td>
</tr>
</table>

---

## ✨ Key Features

| Feature | Description | Status |
|---------|-------------|--------|
| 🧅 **Tor Integration** | Privacy by default with `.onion` circuit routing | ✅ Live |
| 🌐 **HyperNodes** | Encrypted, low-latency P2P routing | ✅ Live |
| 🗄️ **HyperBee Storage** | Decentralized metadata & protocol state | ✅ Live |
| 🔐 **ZK Authentication** | zk-SNARK login — no identity exposed | ✅ Live |
| 🛡️ **DNS Leak Protection** | All DNS routed through Tor | ✅ Live |
| ⚡ **Kill Switch** | Auto-block traffic if VPN drops | ✅ Live |
| 💎 **TUN Mode (Premium)** | Full kernel VPN routing | 🔄 Beta |
| 🧩 **DAO Governance** | Community proposals & voting | 🔄 Building |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                        LASTPARADOX NETWORK                          │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│    ┌──────────┐     ┌──────────┐     ┌──────────┐     ┌──────────┐ │
│    │  Flutter │     │  Node.js │     │   Tor    │     │  Keeper  │ │
│    │  Desktop │◄───►│  Daemon  │◄───►│  SOCKS5  │◄───►│ (.onion) │ │
│    │    UI    │     │ (Fastify)│     │          │     │          │ │
│    └──────────┘     └──────────┘     └──────────┘     └──────────┘ │
│          │                │                                        │
│          │                ▼                                        │
│          │         ┌─────────────────────────┐                     │
│          │         │      Hypercore          │                     │
│          │         │  ┌─────────┐ ┌────────┐ │                     │
│          │         │  │Hyperbee │ │Swarm   │ │                     │
│          │         │  │ (Data)  │ │ (P2P)  │ │                     │
│          │         │  └─────────┘ └────────┘ │                     │
│          │         └─────────────────────────┘                     │
│          │                                                         │
│          ▼                                                         │
│    ┌──────────┐                                                    │
│    │ ZK Proofs│  ◄── Local generation, never uploaded              │
│    │(snarkjs) │                                                    │
│    └──────────┘                                                    │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘

Traffic Flow:
YOU ──► TOR ──► HYPERNODE ──► EXIT ──► INTERNET
  │                 │
  └── ZK Proof ─────┘ (identity never leaked)
```

---

## 📊 Project Status

```
Phase 0 ████████████████░░░░ 80%  ← CURRENT
Phase 1 ░░░░░░░░░░░░░░░░░░░░  0%
Phase 2 ░░░░░░░░░░░░░░░░░░░░  0%
```

| Phase | Focus | Status |
|-------|-------|--------|
| **Phase 0** | Core VPN, Tor, Hypercore, ZK Auth, TUN | 🔄 In Progress |
| **Phase 1** | DAO governance, audits, multi-platform | ⏳ Planned |
| **Phase 2** | Token creation (if DAO approves) | 🔮 Future |

> **Note:** Token creation requires DAO vote. No token exists today.

---

## 💎 Contribution Tiers

> ⚠️ **Important:** Contributions are **service payments**, not investments.  
> See [LEGAL.md](./LEGAL.md) for full terms.

| Tier | Price | What You Get |
|------|-------|--------------|
| 🔹 **Supporter** | $4/year | Basic proxy access, community membership |
| 🔸 **Governance** | $9/year | Full app access, voting rights |
| 💎 **Builder** | $50+ | Early features, priority voice, builder recognition |

<p align="center">
  <strong>No tokens. No presale. No promises.</strong><br/>
  <sub>Just working software and community governance.</sub>
</p>

---

## 📚 Documentation

<table>
<tr>
<td align="center">
<a href="./WHITEPAPER_FINAL.md">
<img src="https://img.shields.io/badge/📄-Whitepaper-7D4698?style=for-the-badge" alt="Whitepaper"/>
</a>
</td>
<td align="center">
<a href="./TOKENOMICS.md">
<img src="https://img.shields.io/badge/💰-Tokenomics-FF6B6B?style=for-the-badge" alt="Tokenomics"/>
</a>
</td>
<td align="center">
<a href="./LEGAL.md">
<img src="https://img.shields.io/badge/⚖️-Legal-gray?style=for-the-badge" alt="Legal"/>
</a>
</td>
</tr>
</table>

---



## ⚠️ Disclaimer

> **This is experimental software.** Use at your own risk.
>
> - No absolute privacy guarantee
> - VPN/Tor may be restricted in some jurisdictions  
> - You are responsible for local law compliance
> - No tokens exist — contributions are service payments
>
> See [LEGAL.md](./LEGAL.md) for complete terms.

---

## 🤝 Community

<p align="center">
  <a href="https://discord.gg/nnZGYNU8Dp">
    <img src="https://img.shields.io/badge/💬_Discord-Join_Community-5865F2?style=for-the-badge" alt="Discord"/>
  </a>
  <a href="https://x.com/LastParadox__">
    <img src="https://img.shields.io/badge/🐦_X-@LastParadox__-000000?style=for-the-badge" alt="X"/>
  </a>
  <a href="https://lastparadox.xyz">
    <img src="https://img.shields.io/badge/🌐_Website-lastparadox.xyz-00C853?style=for-the-badge" alt="Website"/>
  </a>
</p>

<p align="center">
  <a href="mailto:contact@lastparadox.xyz">
    <img src="https://img.shields.io/badge/📧_Email-contact@lastparadox.xyz-EA4335?style=for-the-badge" alt="Email"/>
  </a>
</p>

---

<p align="center">
  <strong>🛡️ Privacy is not a feature. It's the foundation.</strong>
</p>

<p align="center">
  <sub>© 2025 LastParadox Project</sub><br/>
  <sub>Founder: <strong>Last_Exit</strong></sub><br/>
  <sub>All rights reserved — See <a href="./LEGAL.md">LEGAL.md</a></sub>
</p>

---

<p align="center">
  <a href="#top">
    <img src="https://img.shields.io/badge/⬆️_Back_to_Top-7D4698?style=flat-square" alt="Back to Top"/>
  </a>
</p>
