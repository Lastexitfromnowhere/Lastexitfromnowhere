<h1 align="center">📦 Repository Structure</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Public%20Repo-Documentation-46D5E0?style=for-the-badge&labelColor=000000" alt="Public"/>
  <img src="https://img.shields.io/badge/Private%20Repos-Source%20Code-8d929c?style=for-the-badge&labelColor=000000" alt="Private"/>
</p>

---

## What is here

This public repository holds **documentation only** for the LastParadox ecosystem:

```
Lastexitfromnowhere/
├── README.md        # Ecosystem overview — VPN (disappear) + Recovery (reappear)
├── WHITEPAPER.md    # VPN technical overview, threat model, honest limitations
├── SECURITY.md      # How to report a vulnerability
├── LEGAL.md         # Legal notice & disclaimers
└── CODE_NOTICE.md   # This file
```

The application source lives in private repositories.

## Why the code is private (for now)

Honest answer: this is a one-developer studio, and the code has not had an independent review.
Publishing it today would mostly expose half-finished internals, not make anyone safer. We would
rather open it once it is signed, tidied and has had outside eyes on it — **no date is promised**.

What you *can* verify without the source:

- **The parts that matter for safety are already open source and not ours.** LastParadox ships
  the official `tor.exe` and the official pluggable-transport binaries (`snowflake-client`,
  `lyrebird`) unmodified. Our code orchestrates them; it does not touch the cryptography.
- **There is no server to trust.** The VPN has no LastParadox backend in the traffic path.
  Watch the network: the app talks to `127.0.0.1` and to the Tor network, nothing else.
- **Integrity check.** The app hashes its critical binaries on first run and flags any later change.
- **Recovery is read-only by construction.** Its disk layer exposes no write method. Run it from a
  USB stick on a drive you don't care about and watch the write counter stay at zero.

## Private repositories

| Repository | Contents | Stack |
|---|---|---|
| `LastParadox-VPN` | Desktop client + embedded daemon | Flutter / Dart · Tor · tun2socks / wintun |
| `phoenix-recover` | LastParadox Recovery (file recovery) | Native Windows, portable |
| `lastparadox-home`, `LandingLast` | Websites | Static HTML · Cloudflare Workers · Vercel |
| `downloads-worker`, `feedback-worker` | Installer CDN + counter · public feedback page | Cloudflare Workers · R2 · D1 |

## Technology stack

| Layer | Technology | Notes |
|---|---|---|
| Desktop UI | Flutter 3 (Dart) | Windows x64 |
| Local daemon | Dart (embedded in the app) | `127.0.0.1:9124` — replaced the former Node.js daemon |
| Anonymity | Tor (official binary) | SOCKS5, control port, DNS over Tor |
| Censorship bypass | Snowflake, obfs4 (lyrebird) | Tor's official pluggable transports |
| Whole-device routing | tun2socks + wintun | Virtual adapter, kill switch |
| Mobile | Android client | |
| Distribution | Cloudflare R2 + Worker | Stable URL, public download counter |
| Recovery licensing | Ed25519 signed licenses | Verified offline, forever |

Things you may find in older documents or forks that are **no longer part of the product**:
Hypercore / Hyperswarm P2P layer, zero-knowledge (snarkjs) authentication, Keeper VPS, Identity
Shield, Vault password manager, Solana/Stripe contribution tiers, token or DAO plans. They were
removed in the 2026 simplification.

## Want to look at the code?

- **Security researchers** — write to **contact@lastparadox.xyz** with your background and what
  you'd like to review. Read access to a private repo can be arranged case by case.
- **Everyone else** — the fastest way to help is to run the app in the field and tell us what
  breaks: [feedback.lastparadox.dev](https://feedback.lastparadox.dev) or
  [Discord](https://discord.gg/nnZGYNU8Dp).

## Links

<p align="center">
  <a href="https://lastparadox.dev"><img src="https://img.shields.io/badge/🏠_Ecosystem-lastparadox.dev-F5F2EC?style=for-the-badge&labelColor=000000" alt="Ecosystem"/></a>
  <a href="https://lastparadox.xyz"><img src="https://img.shields.io/badge/🧅_VPN-lastparadox.xyz-46D5E0?style=for-the-badge&labelColor=000000" alt="VPN"/></a>
  <a href="https://recovery.lastparadox.dev"><img src="https://img.shields.io/badge/🔥_Recovery-recovery.lastparadox.dev-FF5A1F?style=for-the-badge" alt="Recovery"/></a>
</p>

<p align="center"><sub>© 2025–2026 LastParadox — All rights reserved · See <a href="./LEGAL.md">LEGAL.md</a></sub></p>
