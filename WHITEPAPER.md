# LastParadox VPN — Technical Overview

**Version 2.0 · August 2026**

> This document replaces the 2025 whitepaper. That text described an earlier architecture
> (Hypercore P2P layer, zero-knowledge authentication, contribution tiers, a planned token and DAO).
> **None of that exists in the product today.** In 2026 the project was deliberately simplified to
> the core that actually protects people: a free client that puts the whole device on Tor, and
> connects even where Tor is blocked. What follows describes the software as it ships.

---

## 1. What it is

LastParadox VPN is a **free Windows (and Android) client for the public Tor network** that:

- routes **the entire device** through Tor — every application, not just a browser tab;
- **connects under censorship** using Tor's official pluggable transports (Snowflake, obfs4);
- needs **no account, no payment, no identity**;
- runs **no server of ours**. There is nothing between you and the Tor network that we operate,
  so there is nothing we could log, be compelled to hand over, or have seized.

It is a **privacy and anti-censorship tool**. It is not a streaming VPN, and it is not
Tails-grade anonymity (see §7).

## 2. Who it is for

Journalists, human-rights defenders, NGO field teams, activists and researchers operating where
networks are monitored or censored — and anyone who wants real network privacy without trusting a
company's "no-logs" promise. The design target is a **non-technical person at risk**: one button,
sane defaults, automatic fallbacks.

## 3. Architecture

```
                     ┌───────────────────────── your machine ─────────────────────────┐
                     │                                                                 │
  every app ──► TUN interface ──► tun2socks ──► local SOCKS5 ──► tor.exe ──┐            │
  (browser,     (wintun)                        (127.0.0.1)                │            │
   mail, IM…)                                                              │            │
                     │                                     [pluggable transport]        │
                     │                                      snowflake / obfs4           │
                     └──────────────────────────────────────────────┬────────────────┘
                                                                    │
                                                                    ▼
                                                     TOR NETWORK (3 hops) ──► internet
                                                     thousands of volunteer relays
```

**Components, all local:**

| Component | Role |
|---|---|
| Flutter desktop app (Dart) | UI, settings, connection lifecycle, embedded daemon |
| Embedded daemon (Dart, `127.0.0.1:9124`) | Manages Tor, the SOCKS5/HTTP proxies, TUN, split tunneling, integrity check |
| `tor.exe` (official Tor) | Onion routing, SOCKS `9050`, control port `9051` (cookie auth), DNS `9053` |
| Pluggable transports (`snowflake-client`, `lyrebird`) | Censorship circumvention — Tor's official binaries, unmodified |
| `tun2socks` + `wintun` | Whole-device capture: a virtual network adapter that feeds all IP traffic into the SOCKS proxy |

There is **no LastParadox backend**. The only remote infrastructure we run serves the installer
download (a static object store) and a public feedback page. Neither is in the traffic path.

## 4. Whole-device routing (TUN)

Tor Browser protects one browser. LastParadox creates a virtual network adapter (`wintun`) and
sets it as the default route, so **every** application's TCP traffic and DNS go through Tor
without per-app configuration. UDP that cannot be carried by Tor is dropped rather than leaked.

- **Kill switch** — if Tor or the tunnel drops, traffic fails closed instead of falling back to
  the clear.
- **DNS** — all resolution goes through Tor's `DNSPort`; the ISP resolver is never consulted.
- **Split tunneling** — optional per-domain bypass for things that must not go through Tor
  (e.g. a local printer, a corporate intranet). Off by default.
- **Exit region** — optionally pin the Tor exit to a country (`ExitNodes {cc}`) for
  circumvention purposes. Fewer candidate nodes means slower circuits; this is not a
  geo-unblocking feature.

## 5. Censorship bypass (bridges)

In Iran, China, Russia and elsewhere, the censor blocks Tor *at the entrance* by blacklisting the
public relays and fingerprinting the protocol. Bridges are unlisted entry points, and pluggable
transports disguise the traffic.

LastParadox bundles two of Tor's official transports and drives them through the Tor control
port at runtime (no restart):

| Transport | How it hides | Operational cost |
|---|---|---|
| **Snowflake** | Traffic looks like a WebRTC video call; relayed by thousands of short-lived volunteer proxies discovered via a domain-fronted broker | None — no addresses to distribute or maintain |
| **obfs4** (via lyrebird) | Traffic looks like random bytes; connects to unlisted bridge addresses | Addresses rotate and get blocked; refreshed from the Tor Browser bundle at each release |

**Modes:** `Auto` (default) tries a direct Tor connection, switches to Snowflake if bootstrap
stalls (~45 s, faster if a bridge was needed last time), then obfs4 as a last resort.
`Direct`, `Snowflake` and `obfs4` can also be forced in one click. Bootstrap progress is shown
live so a user in a censored network can see the connection making headway.

Bridges get you *into* Tor. They do not change what Tor exits can reach.

## 6. Threat model

**Protects against**

- Your ISP, local network, or national censor seeing **what** you connect to
- Websites and services learning **your IP address** and location
- Application-level leaks that a browser-only Tor setup misses (mail clients, updaters, chat apps)
- Tor being **blocked outright** at the network edge (via bridges)
- Us: there is no LastParadox server that could log, profile or be subpoenaed

**Does not protect against**

- A compromised machine (malware, keyloggers) — Tor cannot help there
- You logging into accounts tied to your real identity
- Global passive adversaries correlating traffic at both ends of Tor (Tor's known limit)
- Browser fingerprinting — use Tor Browser *on top of* LastParadox for browsing
- Exit-node snooping on unencrypted (non-HTTPS) traffic — same as any Tor client

## 7. Honest limitations

- **Speed.** Three volunteer hops. Expect 300 ms – 2 s latency and modest throughput.
  Fine for browsing, messaging, publishing; not for HD video or large downloads.
- **Streaming and "bot" walls.** Netflix, YouTube and many platforms block or challenge Tor
  exits. LastParadox does not and will not try to defeat that — it would require residential
  exit IPs, i.e. a completely different (and riskier) product.
- **Not Tails.** No amnesic OS, no hardened browser bundled. Strong network privacy,
  accessible to a non-engineer — that is the scope.
- **No 100 % guarantee under censorship.** Transports get blocked and updated; Snowflake is
  the most resilient, obfs4 addresses age.
- **Windows binaries are not yet code-signed**, so SmartScreen shows an "unknown publisher"
  warning. Signing is the next milestone.

## 8. Verification and integrity

- **Integrity check** — the app records SHA-256 hashes of its critical binaries (`tor.exe`,
  transports, `tun2socks`, `wintun.dll`) on first run and flags any later modification.
- **No telemetry.** The app makes no calls home. The download counter on the website counts
  installer downloads at the CDN, not app usage.
- **Tor itself is open source and audited.** We ship the official `tor.exe` and the official
  pluggable-transport binaries unmodified.

## 9. Specifications

| | |
|---|---|
| Platforms | Windows 10/11 (x64) · Android |
| Local ports | daemon `9124` · SOCKS `9050` · control `9051` · DNS `9053` |
| Tor config | `torrc` bundled: cookie auth, `GeoIPFile` for exit selection, client-only (no relay, no hidden service) |
| Storage | `%APPDATA%\com.lastparadox.app\vpn\tor\` — Tor data dir + small settings files (exit country, bridge mode) |
| Installer | ~27 MB Inno Setup; stable URL `download.lastparadox.dev/LastParadox-Setup.exe` |
| Price | Free, forever. No tiers. |

## 10. Sustainability

The VPN has no revenue and needs almost none: it has no servers. The studio is funded by
**LastParadox Recovery**, a paid file-recovery tool (€29, lifetime license, verified offline).
There is no token, no DAO, no airdrop, and none are planned.

## 11. Roadmap (no dates promised)

- Code signing → no SmartScreen warning
- Field pilots with partner NGOs; their feedback drives priorities
- Running our own bridges (visible in public Tor metrics)
- WebTunnel transport · macOS / Linux clients · localization (FR · ES · FA · RU · ZH)

---

*Questions, corrections, field reports: contact@lastparadox.xyz · feedback.lastparadox.dev*
