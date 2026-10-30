# Small Office Network Design and Configuration

## Objective
Design and configure a small office LAN where all devices can communicate.

## Tools
Cisco Packet Tracer, draw.io

## Topology
![Topology](screenshots/02-topology-built.png)

## IP Addressing Table
See [ip-addressing-table.md](ip-addressing-table.md)

## Configuration Summary
- 1 router (R1), 1 switch (SW1), 5 PCs
- Network: 192.168.1.0/24
- Gateway: 192.168.1.1 (R1 Gig0/0)
- PCs: 192.168.1.10 to .14 (static)


## Testing and Results
(paste your test table and screenshots here)

## What I Learned
IP addressing, subnet masks, default gateway, MAC addresses and ARP,
switch vs router roles, straight-through vs crossover cables, ping/ICMP.

## Troubleshooting
(note any problem you hit, e.g. the interface was administratively
down until I ran `no shutdown`)

## Files
- topology.pkt: Packet Tracer file
- screenshots/: evidence of each step
