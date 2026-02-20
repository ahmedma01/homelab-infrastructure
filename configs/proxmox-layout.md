# Proxmox VE Layout

## Host
| Setting        | Value            |
|----------------|------------------|
| Proxmox Web UI | 192.168.0.10:8006|
| Network        | Virgin Media LAN |

## Virtual Machines
| VM ID | Name     | Purpose                          |
|-------|----------|----------------------------------|
| —     | pfSense  | Firewall, router, VLAN, WireGuard|

## LXC Containers
| CT ID | Name               | IP Address      | Purpose                        |
|-------|--------------------|-----------------|--------------------------------|
| —     | Nginx Proxy Manager| 192.168.40.98   | Reverse proxy & TLS termination|
| —     | Media Server       | 192.168.40.99   | Self-hosted media services     |

## Network Bridges
| Bridge | VLAN | Connected To        |
|--------|------|---------------------|
| vmbr0  | —    | WAN / Proxmox UI    |
| vmbr1  | 40   | pfSense LAN + VLANs |
