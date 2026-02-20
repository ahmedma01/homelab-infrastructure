# Network Topology

## Physical Layout
```
ISP Router 
│
├── Proxmox Host (192.168.0.10) ← WAN / Proxmox Web UI
│
└── Managed Switch Port 8 ← LAN trunk to Proxmox

Managed Switch
├── Port 1-7 — Access ports (untagged, PVID 1)
└── Port 8   — Trunk port to Proxmox (tagged VLAN 40)

Management devices → Port 1-7 on switch → accesses pfSense at 192.168.1.1
```

## Logical Layout
```
Virgin Media Router (192.168.0.1)
└── Proxmox Host (192.168.0.10) — accessible via browser at :8006

    └── pfSense VM (WAN: 192.168.0.x, LAN: 192.168.1.1)
        │
        ├── VLAN 40 — Media/Services (192.168.40.0/24)
        │   ├── Nginx Proxy Manager LXC (192.168.40.98)
        │   └── Media Server LXC (192.168.40.99)
        │
        └── WireGuard Peer → DigitalOcean VPS (tunnel gateway)
```
