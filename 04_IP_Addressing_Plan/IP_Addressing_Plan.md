# IP Addressing Plan

## Client
Kago Convenience Stores — Kimberley

## Addressing Block
192.168.19.0/24

## VLAN 10 — Department 1

- Network: 192.168.19.0/25
- Gateway: 192.168.19.1
- Broadcast: 192.168.19.127

| Device | Connection | VLAN | IP Address | Subnet Mask | Default Gateway |
|---|---|---:|---|---|---|
| R1 | G0/0.10 | 10 | 192.168.19.1 | 255.255.255.128 | — |
| AP1 | SW1 Fa0/2 | 10 | Not assigned | — | — |
| PC1 | SW1 Fa0/4 | 10 | 192.168.19.10 | 255.255.255.128 | 192.168.19.1 |
| PC2 | SW1 Fa0/5 | 10 | 192.168.19.11 | 255.255.255.128 | 192.168.19.1 |
| Laptop1 | Wireless via AP1 | 10 | 192.168.19.12 | 255.255.255.128 | 192.168.19.1 |
| Laptop2 | Wireless via AP1 | 10 | 192.168.19.13 | 255.255.255.128 | 192.168.19.1 |

## VLAN 20 — Department 2

- Network: 192.168.19.128/25
- Gateway: 192.168.19.129
- Broadcast: 192.168.19.255

| Device | Connection | VLAN | IP Address | Subnet Mask | Default Gateway |
|---|---|---:|---|---|---|
| R1 | G0/0.20 | 20 | 192.168.19.129 | 255.255.255.128 | — |
| AP2 | SW1 Fa0/3 | 20 | Not assigned | — | — |
| PC3 | SW1 Fa0/6 | 20 | 192.168.19.138 | 255.255.255.128 | 192.168.19.129 |
| PC4 | SW1 Fa0/7 | 20 | 192.168.19.139 | 255.255.255.128 | 192.168.19.129 |
| Laptop3 | Wireless via AP2 | 20 | 192.168.19.142 | 255.255.255.128 | 192.168.19.129 |
| Laptop4 | Wireless via AP2 | 20 | 192.168.19.143 | 255.255.255.128 | 192.168.19.129 |

## Switch Port Assignments

| Switch Port | Connected Device | VLAN |
|---|---|---:|
| Fa0/1 | R1 G0/0 — 802.1Q Trunk | Trunk |
| Fa0/2 | AP1 | 10 |
| Fa0/3 | AP2 | 20 |
| Fa0/4 | PC1 | 10 |
| Fa0/5 | PC2 | 10 |
| Fa0/6 | PC3 | 20 |
| Fa0/7 | PC4 | 20 |

## Design Notes

- The 192.168.19.0/24 addressing block is divided into two /25 subnets.
- VLAN 10 is assigned to Department 1.
- VLAN 20 is assigned to Department 2.
- R1 provides the default gateway for each VLAN using router subinterfaces.
- SW1 Fa0/1 is configured as the 802.1Q trunk toward R1.
- AP1 is connected to Fa0/2 in VLAN 10.
- AP2 is connected to Fa0/3 in VLAN 20.
