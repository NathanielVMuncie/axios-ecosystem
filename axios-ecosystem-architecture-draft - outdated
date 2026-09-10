# Axios Ecosystem — Architecture Documentation

**Version:** 1.0-draft  
**Status:** Active — Under Construction  
**Maintained by:** Nathaniel V. Muncie

---

## Overview

The **Axios Ecosystem** is the underlying hard infrastructure and network fabric that supports local agentic lab operations. It is a distributed, multi-node compute environment purpose-built for AI agent workloads, cloud-integrated pipeline execution, and active development.

All heavy compute is offloaded to Axios Core. Axios Helm operates as the active development terminal. Axios Relay provides remote operational reach. All primary nodes communicate over a secure peer-to-peer mesh via Tailscale, with external routing through Cloudflare.

---

## 1. Hardware Nodes

### Axios Core — Compute Server

| Attribute | Value |
|---|---|
| CPU | Intel Core i7-10700F |
| RAM | 16GB |
| GPU | NVIDIA GTX 1660 Ti |
| OS (Current) | Windows 10 |
| OS (Planned) | Linux (migration pending) |

**Role:** Primary compute node. Handles background execution, processing, and heavy agentic workloads — inference, pipeline orchestration, containerized services, and anything exceeding Helm's hardware ceiling.

**Gate:** Cloudflare tunnel configuration required before any Core-hosted service is exposed externally.

---

### Axios Helm — Primary Terminal

| Attribute | Value |
|---|---|
| Hardware | Asus Chromebook CX1505CKA |
| CPU | Intel Celeron N4500 (1.1GHz, 2C/2T) |
| RAM | 4–8GB LPDDR4X (soldered) |
| Storage | 64–128GB eMMC |
| OS | ChromeOS + Crostini (Debian Linux) |
| Shell | Zsh |

**Role:** Active development terminal. All scripting, repository management, and command-line execution originates here.

**Hard Constraints:**
- Zero local-compute architecture enforced — Helm is an edge terminal only
- Crostini kernel lacks `CONFIG_ZRAM` — Zram is impossible; do not re-attempt
- Heavy compute, containerization, and AI inference route to Core or cloud — never executed locally

---

### Axios Relay — Mobile Dispatch

| Attribute | Value |
|---|---|
| Hardware | Samsung Galaxy A12 |

**Role:** Remote instruction relay. Mobile prompt dispatching and operational monitoring. Not a compute node.

---

### Auxiliary Devices

**Role:** Mock testing environments only. Used strictly for cross-platform deployment validation. Not part of the primary compute fabric.

---

## 2. Networking & Routing

### Tailscale Mesh

All primary nodes (Core, Helm, Relay) are integrated via a secure, peer-to-peer Tailscale mesh network. Enables seamless cross-device communication and data transmission regardless of physical location.

### Cloudflare

External routing and tunnel management. The Cloudflare tunnel on Axios Core is the prerequisite gate for exposing any Core-hosted service externally.

**Status:** Tunnel configuration pending.

### Network Topology (Logical)

```
[ Axios Relay (Mobile) ]
          |
          | Tailscale mesh
          |
[ Axios Helm (Terminal) ] ──── Tailscale ──── [ Axios Core (Compute) ]
                                                        |
                                               Cloudflare Tunnel
                                                        |
                                              [ External / Cloud Layer ]
```

---

## 3. Naming Conventions (Mandatory)

| Context | Convention | Example |
|---|---|---|
| Salesforce fields / variables / configs | `snake_case` | `purchasing_timeline__c` |
| Files / repos / external assets | `kebab-case` | `project-brief-summary.md` |
| Portfolio projects | `Salesforce Case Study: [Object] — [Subtitle]` | `Salesforce Case Study: Lead — Priority Level Automation` |

No `ALL_CAPS` general filenames.

---

## 4. Operational Directives

1. **Compute boundary:** Helm is an edge terminal. Any workload exceeding its hardware ceiling routes to Core or cloud.
2. **Core tunnel gate:** No Core-hosted services are exposed until the Cloudflare tunnel is configured and verified.
3. **Repository integrity:** No automated pushes or destructive operations on any external repository without explicit user confirmation.
4. **Scope:** Confine all code changes and generations strictly to requested features or bug fixes.
5. **Communication:** Flag deviations from naming conventions or structural standards before implementation.

---

## 5. Roadmap Gates

| Gate | Dependency | Unlocks |
|---|---|---|
| Axios Core — Linux migration | Hardware / scheduling | Full containerization, stable inference runtime |
| Cloudflare tunnel — Core | Linux migration or Windows config | External service exposure |
| Axios Core — agentic workloads | Tunnel + runtime stable | Heavy inference, background agents |
