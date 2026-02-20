# 🏠 Personal Infrastructure & Security Lab

A self-hosted homelab built on enterprise-grade open-source tools, designed 
to mirror real-world network architecture and security practices. This lab 
simulates how organisations segment networks, manage remote access securely, 
and expose services to the internet safely — all running on repurposed 
hardware at home.

## 📋 Overview
This project started as a way to learn networking and cybersecurity hands-on, 
beyond what any course could teach. Rather than just reading about VLANs and 
firewalls, I built a working environment where I could configure, break, and 
fix things myself.

The lab runs on a Type-1 hypervisor managing multiple VMs and containers, 
with a dedicated firewall handling routing, VLAN segmentation, and DMZ 
isolation. Remote access is handled via a WireGuard VPN tunnel routed through 
a cloud VPS — solving the real-world problem of accessing a home network 
sitting behind CGNAT without exposing a home IP address.

This project demonstrates my understanding of enterprise network design, 
firewall configuration, containerisation, and secure service exposure.

## 🛠️ Tech Stack
| Tool | Purpose |
|------|---------|
| Proxmox VE | Type-1 Hypervisor |
| pfSense | Firewall & Router |
| WireGuard | VPN / Remote Access |
| Nginx Proxy Manager | Reverse Proxy & TLS |
| Docker / LXC | Containerisation |
| Cloudflare | DNS & Wildcard Certificates |

## ✨ Key Features
- **Type-1 Hypervisor** — Proxmox VE managing VMs and LXC containers with high availability
- **VLAN Segmentation** — Network separated into isolated segments with a dedicated DMZ
- **CGNAT Bypass** — WireGuard tunnel via cloud VPS for secure remote access without exposing home IP
- **Reverse Proxy** — Nginx Proxy Manager routing traffic to internal services with TLS termination
- **Wildcard Certificates** — Automated cert issuance via Cloudflare DNS challenge across all subdomains
- **Firewall Rules** — pfSense rules enforcing strict traffic flow between VLANs

## 📸 Screenshots

### Proxmox Dashboard
<img width="1920" height="890" alt="Screenshot 2026-02-20 at 17 59 11" src="https://github.com/user-attachments/assets/e0e737ab-93f1-45b1-baa7-670d0c5ca86d" />


### pfSense Firewall Dashboard
<img width="1457" height="769" alt="pfsene dash board" src="https://github.com/user-attachments/assets/d32ef2fb-64d2-4c11-9ec6-7df8598ff436" />


> 📁 Additional screenshots (VLAN config, firewall rules, WireGuard, Nginx, Cloudflare) available in the [screenshots folder](./screenshots/)


## 📐 How It Works
1. All services run as VMs or LXC containers inside **Proxmox VE**
2. **pfSense** handles all routing, with VLANs separating internal, DMZ, and management traffic
3. Public-facing services sit in the **DMZ**, isolated from the internal network by firewall rules
4. A **WireGuard tunnel** connects the home network to a cloud VPS, allowing secure remote access without exposing the home IP
5. **Nginx Proxy Manager** sits in the DMZ, terminating TLS and reverse proxying HTTPS traffic to internal services
6. **Cloudflare** handles DNS and issues wildcard certificates via DNS challenge

## 🔮 Future Improvements
- Deploy a SIEM (Wazuh or Elastic Stack) to monitor internal traffic and generate alerts
- Add an IDS/IPS (Suricata) inside pfSense for deep packet inspection
- Set up automated backups of VMs to an offsite location
- Expand VLAN structure to include an IoT isolation segment
- Deploy a self-hosted password manager (Vaultwarden) in the DMZ

## ❓ Why This Project?
I built this lab to:
- Go beyond theory and learn networking and security through real hands-on experience
- Understand how enterprise infrastructure is designed and secured
- Solve a real problem — secure remote access on a CGNAT home network
- Build a platform I can keep expanding as I learn more
- Demonstrate practical skills to back up my studies and certifications
