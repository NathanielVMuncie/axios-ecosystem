# Axios Ecosystem

Hard infrastructure and network fabric for local agentic lab operations.

**Notion Project Page:** https://app.notion.com/p/3b73a36cfb2b81df80c8e33276403ab3

## Nodes

| Node | Role | Hardware |
|---|---|---|
| Axios Core | Compute server | Intel i7-10700F · 16GB · GTX 1660 Ti |
| Axios Helm | Primary terminal | ASUS CX1505CKA · ChromeOS + Crostini |
| Axios Relay | Mobile dispatch | Samsung Galaxy A12 |

## Network

- **Tailscale** — peer-to-peer mesh across all primary nodes
- **Cloudflare** — external routing and tunnel (pending configuration on Core)

## Status

Axios Core: Windows 10 — Linux migration pending. Cloudflare tunnel required before external service exposure.

## Research

- [`research/methodology/`](research/methodology/) — proposals, independent audit, and the current pilot-ready deep-research methodology candidate

## Roadmap

| Gate | Dependency | Unlocks |
|---|---|---|
| Linux migration | Hardware / scheduling | Containerization, stable runtime |
| Cloudflare tunnel | Linux migration or Windows config | External service exposure |
| Agentic workloads | Tunnel + runtime stable | Heavy inference, background agents |

