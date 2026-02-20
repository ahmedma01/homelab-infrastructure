# 🏠 Personal Infrastructure & Security Lab

A self-hosted homelab built on enterprise-grade open-source tools, 
designed to mirror real-world network architecture and security practices.

## 📋 Overview
This lab simulates an enterprise network environment at home, featuring 
a Type-1 hypervisor, network segmentation, secure remote access, and 
TLS-terminated reverse proxying across self-hosted services.

## 🛠️ Tech Stack
| Tool | Purpose |
|------|---------|
| Proxmox VE | Type-1 Hypervisor |
| pfSense | Firewall & Router |
| WireGuard | VPN / Remote Access |
| Nginx Proxy Manager | Reverse Proxy & TLS |
| Docker / LXC | Containerisation |
| Cloudflare | DNS & Certificates |

## 🖥️ Proxmox Dashboard
<img width="1920" height="890" alt="Screenshot 2026-02-20 at 17 59 11" src="https://github.com/user-attachments/assets/fd24cc88-dfb6-42e7-ae56-995e9333ed82" />


## 🔒 pfSense Firewall & DMZ VLAN
<img width="1457" height="769" alt="pfsene dash board" src="https://github.com/user-attachments/assets/5ca570f0-0a20-41e3-b85a-37072217ac84" />


## 🔁 Nginx Proxy Manager
<img width="1457" height="766" alt="nginx proxy hosts" src="https://github.com/user-attachments/assets/aadcdeb1-eab4-4cc9-a42a-ad67308263c4" />


## 📐 Architecture
- VLAN segmentation isolating services into a DMZ
- WireGuard gateway on cloud VPS to bypass CGNAT without exposing home IP
- Nginx Proxy Manager terminating TLS and routing to internal services
- Wildcard certificates via Cloudflare DNS challenge across all subdomains

## 🎯 What I Learned
- How enterprise networks segment traffic using VLANs and firewall rules
- How reverse proxies and TLS termination work in practice
- Secure remote access design for restrictive home networks
- How enterprise networks segment traffic using VLANs and firewall rules
- How reverse proxies and TLS termination work in practice
- Secure remote access design for restrictive home networks
