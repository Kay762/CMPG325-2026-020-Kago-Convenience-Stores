# IP Addressing Plan

## Client
Kago Convenience Stores — Kimberley

## Addressing Block
192.168.19.0/24

## VLAN 10 — Department 1

- Network: 192.168.19.0/25
- Gateway: 192.168.19.1
- Broadcast: 192.168.19.127

| Device | Interface | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|---|
| R1 | G0/0.10 | 192.168.19.1 | 255.255.255.128 | — |
| PC1 | Fa0 | 192.168.19.10 | 255.255.255.128 | 192.168.19.1 |
| PC2 | Fa0 | 192.168.19.11 | 255.255.255.128 | 192.168.19.1 |
| Laptop1 | Wireless | 192.168.19.12 | 255.255.255.128 | 192.168.19.1 |
| Laptop2 | Wireless | 192.168.19.13 | 255.255.255.128 | 192.168.19.1 |

## VLAN 20 — Department 2

- Network: 192.168.19.128/25
- Gateway: 192.168.19.129
- Broadcast: 192.168.19.255

| Device | Interface | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|---|
| R1 | G0/0.20 | 192.168.19.129 | 255.255.255.128 | — |
| PC3 | Fa0 | 192.168.19.138 | 255.255.255.128 | 192.168.19.129 |
| PC4 | Fa0 | 192.168.19.139 | 255.255.255.128 | 192.168.19.129 |
| Laptop3 | Wireless | 192.168.19.142 | 255.255.255.128 | 192.168.19.129 |
| Laptop4 | Wireless | 192.168.19.143 | 255.255.255.128 | 192.168.19.129 |

## Design Notes

- The 192.168.19.0/24 addressing block is divided into two /25 subnets.
- VLAN 10 is assigned to Department 1.
- VLAN 20 is assigned to Department 2.
- R1 provides the default gateway for each VLAN using router subinterfaces.
- The two departments remain logically separated using VLANs.
