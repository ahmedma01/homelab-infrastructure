# Managed Switch Configuration

## VLAN Table
| VLAN ID | VLAN Name   | Member Ports | Tagged Ports | Untagged Ports |
|---------|-------------|--------------|--------------|----------------|
| 1       | Default     | 1-8          | 1-7          | 4              |
| 40      | DMZ-VLAN    | 8            | 8            | —              |

## PVID Settings
| Port | PVID |
|------|------|
| 1    | 1    |
| 2    | 1    |
| 3    | 1    |
| 4    | 1    |
| 5    | 1    |
| 6    | 1    |
| 7    | 1    |
| 8    | 1    |

## Notes
- Port 8 is the trunk port connecting the switch to Proxmox
- VLAN 40 traffic is tagged on port 8 and handed to pfSense inside Proxmox
- Connecting to ports 1-7 gives access to pfSense LAN at 192.168.1.1
