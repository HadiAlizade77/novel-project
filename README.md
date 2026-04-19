# Internet Freedom Toolkit — ابزارهای آزادی اینترنت

A suite of open-source tools to restore internet freedom for civilians facing
advanced censorship systems.

## Tools

| Tool | Purpose |
|------|---------|
| [stealth-bridge](./stealth-bridge/) | Traffic camouflage engine — defeats DPI + entropy analysis |
| [dns-escape](./dns-escape/) | DNS freedom layer — tunnels DNS over allowed HTTPS |
| [samizdat](./samizdat/) | File distribution network — splits, disguises, reassembles files |
| [watchtower](./watchtower/) | Signal intelligence dashboard — monitors censorship state |
| [freedom-wiki](./freedom-wiki/) | Circumvention knowledge base — offline PWA in Farsi |
| [lifeline](./lifeline/) | Bridge distribution system — decentralized bridge discovery |

## Quick Start

```bash
# Build all tools
make all

# Run the bridge server (on a VPS outside the country)
./stealth-bridge/bin/server -config server.yaml

# Run the bridge client (on a device inside the country)
./stealth-bridge/bin/client -bridge YOUR_BRIDGE_ADDR -secret YOUR_SECRET

# Start the local DNS resolver
./dns-escape/bin/dns-escape -listen 127.0.0.1:53

# Split a file for distribution
./samizdat/bin/split -file tool.exe -out ./chunks/

# Run a watchtower probe
./watchtower/bin/probe -report https://YOUR_DASHBOARD
```

## Threat Model

These tools are designed against:

- **Deep Packet Inspection (DPI)** — 3rd generation behavioral + payload signatures
- **Entropy analysis** — monitoring traffic entropy and packet size distribution
- **Protocol blocking** — UDP/ICMP/IPv6 completely blocked; TCP 443 is the only path
- **DNS interception** — all DNS forced to national resolver
- **CDN blocking** — foreign CDNs blocked or heavily monitored
- **48-hour identification** — traffic analysis can identify users within 48 hours on mobile

## Principles

- All tools are **defensive only** — enabling access to information
- **Panic button** in every tool — removes all traces cleanly
- **No offensive capabilities** — cannot be repurposed for attacks
- **User safety first** — OPSEC guides included in Farsi
- Minimize forensic footprint

## Building

Requires Go 1.21+.

```bash
make all       # Build everything
make test      # Run tests
make clean     # Remove binaries
```

## Ethics & Legal

These tools enable access to the open internet. Use them to read news, communicate
with family, and access educational resources. Do not use them for illegal activities.

---

*"Information is the oxygen of the modern age."*
