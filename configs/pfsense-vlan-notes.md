# pfSense VLAN Configuration Notes

## VLANs Configured
| VLAN ID | Name | Purpose |
|---------|------|---------|
| 10 | LAN | Internal trusted devices |
| 20 | DMZ | Public facing services |
| 30 | Management | Proxmox and network devices |

## Firewall Rule Logic
- DMZ can only receive traffic on ports 80/443
- DMZ cannot initiate connections to LAN
- Management VLAN accessible only from LAN
- WireGuard traffic routed through VPS gateway
