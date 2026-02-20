# 🏠 Personal Infrastructure & Security Lab

A self-hosted homelab built on enterprise-grade open-source tools, 
designed to mirror real-world network architecture.

## 🛠️ Tech Stack
- **Hypervisor:** Proxmox VE (Type-1)
- **Firewall/Router:** pfSense
- **VPN:** WireGuard
- **Reverse Proxy:** Nginx Proxy Manager
- **Containerisation:** Docker, LXC
- **DNS/TLS:** Cloudflare DNS challenge, wildcard certificates

## 📐 Architecture
- VLAN segmentation isolating services into a DMZ
- WireGuard gateway on cloud VPS to bypass CGNAT and avoid exposing home IP
- Nginx Proxy Manager terminating TLS and routing traffic to internal services
- Wildcard certificates issued across all subdomains via Cloudflare

## 🎯 What I learned
- How enterprise networks segment traffic using VLANs and firewall rules
- How reverse proxies and TLS termination work in practice
- Secure remote access design for restrictive home networks
