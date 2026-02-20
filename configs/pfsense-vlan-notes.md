# pfSense Interface & VLAN Configuration

## Interfaces
| Interface | Name   | IP Address      | Purpose                        |
|-----------|--------|-----------------|--------------------------------|
| WAN       | WAN    | 192.168.0.x     | Uplink to ISP router  |
| LAN       | LAN    | 192.168.1.1     | Internal trusted network       |
| VLAN 40   | MEDIA  | 192.168.40.1    | Media servers and DMZ services |

## VLAN 40 DHCP Server
| Setting     | Value                         |
|-------------|-------------------------------|
| Subnet      | 192.168.40.0/24               |
| Gateway     | 192.168.40.1                  |
| DHCP Range  | 192.168.40.100 - 192.168.40.200 |
| Nginx LXC   | 192.168.40.98 (static)        |
| Media LXC   | 192.168.40.99 (static)        |

## Firewall Rule Logic
- VLAN 40 can only receive inbound traffic on ports 80 and 443
- VLAN 40 cannot initiate connections to the LAN (192.168.1.0/24)
- LAN can initiate connections to VLAN 40 for management
- WireGuard tunnel routes through DigitalOcean VPS gateway
- Nginx Proxy Manager handles all TLS termination for VLAN 40 services
