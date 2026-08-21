<h1 align="center">🔒 Security Policy</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Responsible%20Disclosure-Welcome-46D5E0?style=for-the-badge&labelColor=000000" alt="Disclosure"/>
  <img src="https://img.shields.io/badge/Bug%20Bounty-None%20(indie%20studio)-8d929c?style=for-the-badge&labelColor=000000" alt="Bounty"/>
</p>

---

## Reporting a vulnerability

<p align="center">
  <a href="mailto:contact@lastparadox.xyz">
    <img src="https://img.shields.io/badge/📧_Email-contact@lastparadox.xyz-EA4335?style=for-the-badge" alt="Security Email"/>
  </a>
</p>

> **Please do not open public GitHub issues for security-sensitive reports.**
> Our users include people for whom a leaked flaw is not an inconvenience but a danger.
> Give us a chance to fix it first.

### What to include

| | |
|---|---|
| **Summary** | What the issue is |
| **Severity** | Your assessment (Critical / High / Medium / Low) |
| **Steps to reproduce** | Enough for us to see it ourselves |
| **Impact** | What an attacker could achieve — especially: can it **deanonymize** or **leak traffic**? |
| **Component** | VPN app, daemon, Recovery, a website, a Worker |
| **Suggested fix** | Optional, appreciated |

### What to expect

| Stage | Timeframe |
|---|---|
| Acknowledgment | Within 72 hours |
| Initial assessment | Within 7 days |
| Status updates | As progress is made — we are a very small team, we will be honest about pace |
| Fix | Prioritized by severity; traffic-leak and deanonymization issues first |
| Disclosure | Coordinated with you, after a fix ships |

---

## Scope

### In scope

| Component | What it is |
|---|---|
| ✅ **LastParadox VPN** (Windows, Android) | The client, its embedded daemon, TUN/kill-switch/DNS logic, bridge handling, integrity check |
| ✅ **LastParadox Recovery** | The file-recovery tool — **any write to a scanned drive is a critical bug** |
| ✅ **Websites & Workers** | `lastparadox.dev`, `lastparadox.xyz`, `recovery.lastparadox.dev`, `download.lastparadox.dev`, `feedback.lastparadox.dev` |
| ✅ **Installer & update path** | Tampering, downgrade, hash mismatches |

**Highest priority:** anything that makes traffic bypass Tor (leaks on connect/disconnect, DNS,
IPv6, split-tunnel misconfiguration), or that exposes a user's real IP.

### Out of scope

| Item | Why |
|---|---|
| ❌ Tor network / protocol issues | Report to the [Tor Project](https://www.torproject.org/) |
| ❌ Snowflake / obfs4 / lyrebird internals | Report to the Tor anti-censorship team — we ship their binaries unmodified |
| ❌ Third-party dependencies | Report upstream (we will still appreciate a heads-up) |
| ❌ "Tor is slow" / Tor exits blocked by a platform | By design, not a vulnerability |
| ❌ Social engineering, physical access | Not a software flaw |
| ❌ Denial of service | Unless it causes traffic to leak or data to be lost |
| ❌ SmartScreen "unknown publisher" warning | Known — binaries are not yet code-signed |

---

## Security measures in place

| Layer | Implementation |
|---|---|
| **Anonymity** | Official Tor client, 3-hop onion routing, client-only config (no relay, no hidden service) |
| **Censorship resistance** | Snowflake and obfs4 pluggable transports, automatic fallback |
| **Whole-device capture** | wintun virtual adapter + tun2socks; non-Tor-capable UDP dropped, not leaked |
| **Kill switch** | Fail-closed when Tor or the tunnel drops |
| **DNS** | All resolution through Tor's DNSPort |
| **Control port** | Cookie authentication, bound to `127.0.0.1` |
| **Integrity** | SHA-256 of `tor.exe`, transports, `tun2socks`, `wintun.dll` recorded on first run, verified after |
| **No backend** | No LastParadox server in the traffic path — nothing to log, breach or seize |
| **No telemetry** | The app never calls home |
| **Recovery** | Read-only disk layer by construction; Ed25519 licenses verified offline |

---

## Recognition

There is no paid bug bounty — this is an independent studio with no investors. What we can do:

- Credit you in release notes and here, in a Hall of Fame (with your permission)
- Say thank you publicly, and mean it
- Never take legal action against good-faith research that follows this policy

### Hall of Fame

*Nobody yet. Be the first.*

---

## Contact

| Purpose | Contact |
|---|---|
| Security reports | contact@lastparadox.xyz — put **[SECURITY]** in the subject |
| General | contact@lastparadox.xyz |
| Community | [Discord](https://discord.gg/nnZGYNU8Dp) |

<p align="center"><strong>🛡️ Security is not a feature. It's the foundation.</strong></p>
<p align="center"><sub>Thank you for helping keep LastParadox users safe.</sub></p>
