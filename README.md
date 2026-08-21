<h1 align="center">L A S T &nbsp; P A R A D O X</h1>

<h3 align="center">
  <em><span>Disappear.</span> <span>Reappear.</span></em>
</h3>

<p align="center">
  We build both ends of the digital paradox:<br/>
  the art of <strong>disappearing without a trace</strong>, and the art of <strong>bringing back what was lost</strong>.<br/>
  <sub>Two tools. One conviction — <strong>cryptography over promises</strong>.</sub>
</p>

<p align="center">
  <a href="https://lastparadox.dev">
    <img src="https://img.shields.io/badge/🏠_ECOSYSTEM-lastparadox.dev-F5F2EC?style=for-the-badge&labelColor=000000" alt="Ecosystem"/>
  </a>
  <a href="https://lastparadox.xyz">
    <img src="https://img.shields.io/badge/🧅_VPN-lastparadox.xyz-46D5E0?style=for-the-badge&labelColor=000000" alt="VPN"/>
  </a>
  <a href="https://recovery.lastparadox.dev">
    <img src="https://img.shields.io/badge/🔥_Recovery-recovery.lastparadox.dev-FF5A1F?style=for-the-badge" alt="Recovery"/>
  </a>
</p>

<p align="center">
  <a href="https://discord.gg/nnZGYNU8Dp">
    <img src="https://img.shields.io/badge/Discord-Join%20Us-5865F2?style=flat-square&logo=discord&logoColor=white" alt="Discord"/>
  </a>
  <a href="https://x.com/LastParadox__">
    <img src="https://img.shields.io/badge/X-Follow-000000?style=flat-square&logo=x&logoColor=white" alt="X"/>
  </a>
</p>

---

## ⚖️ The Paradox

<table>
<tr>
<td align="center" width="50%">
<h3>🧅 LastParadox VPN</h3>
<em>Disappear. For real.</em><br/><br/>
A <strong>free</strong> Tor VPN that routes your <strong>whole device</strong> through Tor —
not just a browser tab — and connects <strong>even where Tor is blocked</strong>.
<strong>Zero logs</strong> (there's no server of ours that could log), no account, no payment.<br/><br/>
<img src="https://img.shields.io/badge/Status-Live-00C853?style=flat-square" alt="Live"/>
<img src="https://img.shields.io/badge/Price-Free%20forever-46D5E0?style=flat-square" alt="Free"/><br/><br/>
<a href="https://lastparadox.xyz"><strong>lastparadox.xyz →</strong></a>
</td>
<td align="center" width="50%">
<h3>🔥 LastParadox Recovery</h3>
<em>Reappear. From the ashes.</em><br/><br/>
File recovery for Windows. Deleted, emptied recycle bin, formatted —
<strong>free unlimited scan &amp; preview</strong>, strict read-only engine.
You only pay if your files are recoverable.<br/><br/>
<img src="https://img.shields.io/badge/Status-Live-00C853?style=flat-square" alt="Live"/>
<img src="https://img.shields.io/badge/License-%E2%82%AC29%20lifetime-FF5A1F?style=flat-square" alt="29 lifetime"/><br/><br/>
<a href="https://recovery.lastparadox.dev"><strong>recovery.lastparadox.dev →</strong></a>
</td>
</tr>
</table>

### 🧬 Same DNA on both sides

| | |
|---|---|
| 🚫 **Zero trusted servers** | The VPN runs on the public Tor network — there is no server of ours between you and the internet. Recovery's licenses verify offline, forever. What doesn't exist can't be seized, cut off, or resold. |
| 🔑 **Verify, don't trust** | We don't ask you to believe a privacy policy. The VPN *can't* log you by architecture; Recovery *can't* write to your disk by design. Both are provable, not promised. |
| 🪶 **Native, tiny, auditable** | Native binaries of a few MB. No telemetry anywhere. Your data never leaves your machine. |
| 🌩️ **Built for the bad days** | A reporter under surveillance, a dying drive: our tools serve when things go wrong — that's exactly when they're not allowed to lie. |

---

## 🧅 LastParadox VPN — Disappear

<p align="center">
  <img src="https://img.shields.io/badge/Status-Live%20(v2.0)-00C853?style=for-the-badge" alt="Status"/>
  <img src="https://img.shields.io/badge/Price-Free%20forever-46D5E0?style=for-the-badge&labelColor=000000" alt="Free"/>
  <img src="https://img.shields.io/badge/Platform-Windows%20·%20Android-46D5E0?style=for-the-badge&labelColor=000000" alt="Platform"/>
</p>

<h3 align="center">
  <em>Privacy is not a luxury. It's a right — especially for those who need it most.</em>
</h3>

Most VPNs ask you to **trust** their "no-logs" promise. LastParadox makes logging
**technically impossible**: it routes your entire device through the **public Tor
network**, so there is no server of ours that could keep a log. No account, no
payment, no telemetry — **free for everyone, forever**.

Built first for **journalists, human rights defenders, NGOs and activists** in
high-risk environments — and free for anyone who values real network privacy.

> **Honest scope:** this is a privacy / anti-censorship tool, **not** a streaming VPN
> (Tor exits are blocked by Netflix &amp; co.), and **not** Tails-grade anonymity. It gives
> you network-level privacy — your IP hidden from every app, your ISP blind, censorship
> bypassed — accessible to a non-technical person at risk.

### ✨ Features

| Feature | Description | Status |
|---------|-------------|--------|
| 🖥️ **Whole-device Tor (TUN)** | Every app on your machine through Tor — not just a browser tab | ✅ Live |
| 🌉 **Censorship bypass** | Tor blocked where you are (Iran, China, Russia)? Snowflake &amp; obfs4 bridges kick in automatically — Tor's official pluggable transports, nothing homemade | ✅ Live |
| 🌍 **Exit region** | Pick your Tor exit country (US, DE, FR, NL…) | ✅ Live |
| 🧩 **Split tunneling** | Route or bypass specific domains | ✅ Live |
| 🛡️ **DNS leak protection** | All DNS routed through Tor | ✅ Live |
| ⚡ **Kill switch** | Auto-block traffic if the tunnel drops | ✅ Live |
| 🔒 **Integrity check** | SHA-256 verification of bundled binaries (tamper detection) | ✅ Live |
| 🚫 **No account** | Works on install — no sign-up, no email, no identity | ✅ Live |

### 🏗️ How it works

```
YOU ──► LastParadox (local daemon) ──► [bridge if Tor is blocked] ──► TOR (public network) ──► INTERNET
             │                              Snowflake · obfs4
             └── bundles Tor + SOCKS5 + a whole-device TUN interface
                 nothing runs on our servers — there are none
```

**Honest scope:** bridges get you *into* Tor where Tor is censored. They don't change what
Tor exits can reach — streaming platforms still block them, and no app can guarantee 100% access.

<p align="center">
  <a href="https://download.lastparadox.dev/LastParadox-Setup.exe">
    <img src="https://img.shields.io/badge/⬇️_Download_free-Windows-46D5E0?style=for-the-badge&labelColor=000000" alt="Download"/>
  </a>
  <a href="https://feedback.lastparadox.dev">
    <img src="https://img.shields.io/badge/💬_Feedback-feedback.lastparadox.dev-46D5E0?style=for-the-badge&labelColor=000000" alt="Feedback"/>
  </a>
</p>

---

## 🔥 LastParadox Recovery — Reappear

**Deleted files, emptied recycle bin, formatted drives** — as long as nothing has
overwritten them, your files are still there. Recovery finds them, you **see them
with your own eyes**, and you only pay if they're recoverable.

| | |
|---|---|
| 🔍 **NTFS / FAT undelete** | Files come back with their real name, folder and date — emptied recycle bin included |
| 🧬 **Deep carve** | Sector-by-sector signature scan, 40+ formats (jpg, cr2 RAW, psd, heic, mp4, mkv, pdf, zip, pst…) — works after formatting |
| 🔒 **Read-only by architecture** | The engine's only disk interface has no write method. Not a promise — a design |
| 🪶 **1.9 MB, portable** | Runs from a USB stick — never installs onto the drive you're saving |
| 🔑 **Offline Ed25519 license** | €29 once, lifetime. Verifies locally, forever — even if our servers vanish |

<p align="center">
  <a href="https://recovery.lastparadox.dev">
    <img src="https://img.shields.io/badge/⬇️_Free_scan-recovery.lastparadox.dev-FF5A1F?style=for-the-badge" alt="Download"/>
  </a>
</p>

---

## 🛠️ Also built

Beyond the paradox — other things I ship as a developer:

| | | |
|---|---|---|
| 🦺 **ModeOp SS4** | French regulatory SaaS — generates compliant asbestos sub-section 4 work procedures in 20 minutes. Every value sourced and dated (NF X46-102, VLEP, RAAT). | [modeop.lastparadox.dev](https://modeop.lastparadox.dev/) |
| 🏈 **BL Study & Sports Consulting** | Bilingual site for a US-based agency guiding European athletes to NCAA / NAIA / NJCAA scholarships — from profile review to signature. | [blstudysportsconsulting.com](https://www.blstudysportsconsulting.com/) |

---

## ⚠️ Disclaimer

> **Privacy tool (VPN) / data recovery depends on drive state (Recovery).**
>
> - No absolute anonymity guarantee — this is network privacy, not Tails-grade anonymity
> - Not a streaming/geo-unblocking VPN (Tor exits are blocklisted by streaming services)
> - Overwritten data is physically unrecoverable
> - Tor may be restricted in some jurisdictions — you are responsible for local law compliance
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
  <a href="https://feedback.lastparadox.dev">
    <img src="https://img.shields.io/badge/💬_Feedback-Leave_yours-46D5E0?style=for-the-badge&labelColor=000000" alt="Feedback"/>
  </a>
</p>

<p align="center">
  <a href="mailto:contact@lastparadox.dev">
    <img src="https://img.shields.io/badge/📧_Email-contact@lastparadox.dev-EA4335?style=for-the-badge" alt="Email"/>
  </a>
</p>

---

<p align="center">
  <strong>🛡️ Privacy is not a feature. It's the foundation.</strong><br/>
  <strong>🔥 And what was lost can rise again.</strong>
</p>

<p align="center">
  <sub>© 2025–2026 LastParadox</sub><br/>
  <sub>All rights reserved — See <a href="./LEGAL.md">LEGAL.md</a></sub>
</p>
