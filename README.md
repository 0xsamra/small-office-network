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
<img width="556" height="454" alt="03-pc1-ip-config" src="https://github.com/user-attachments/assets/41841208-e6dd-4fd7-b25b-4c2423cfbdee" />

---

<img width="488" height="252" alt="04-pc1-ipconfig" src="https://github.com/user-attachments/assets/275c45a4-dd79-401e-abb3-ef5cc16ef27f" />

---

<img width="482" height="194" alt="05-pc-to-pc-ping" src="https://github.com/user-attachments/assets/60d8d7af-ba08-4b94-99dd-6fda88fc3580" />

---

<img width="492" height="209" alt="06-router-interface-status" src="https://github.com/user-attachments/assets/44e699e0-2552-49cf-a1ae-a25d40fa6a87" />

---

<img width="487" height="198" alt="07-ping-to-gateway" src="https://github.com/user-attachments/assets/51acde29-109f-45b0-818c-00e75f4b558f" />

---
<img width="331" height="327" alt="08-router-congig" src="https://github.com/user-attachments/assets/828a5791-b8aa-428c-913c-bfc719acdad2" />

---
<img width="491" height="381" alt="09-pc-to-pc-ping" src="https://github.com/user-attachments/assets/af1aea89-166c-4114-8b46-6553bb118ef5" />

---

<img width="495" height="312" alt="10-router-to-pc-ping" src="https://github.com/user-attachments/assets/b965b72b-260f-4841-b547-d785c530f7cc" />

---
<img width="487" height="118" alt="11-arp-table" src="https://github.com/user-attachments/assets/dec48fba-b437-4a7c-a138-fcb58f5cd1b9" />

---

## What I Learned
IP addressing, subnet masks, default gateway, MAC addresses and ARP,
switch vs router roles, straight-through vs crossover cables, ping/ICMP.

## Troubleshooting
## Troubleshooting

**Issue 1: Ping from PC1 to the gateway failed (100% packet loss)**
- Cause: The router interface GigabitEthernet0/0 was not fully configured
  and active. Router interfaces are shut down by default.
- Fix: Assigned the IP address 192.168.1.1/24 and ran `no shutdown`.
- Verification: `show ip interface brief` showed up/up, and pings
  to 192.168.1.1 then succeeded.

**Issue 2: "Invalid input detected" when pinging from the router**
- Cause: I ran `ping` in global configuration mode (`R1(config)#`),
  where it is not available.
- Fix: Returned to privileged mode with `end` (or used `do ping`).

**Note:** The first ping in each test sometimes timed out because
ARP had to resolve the MAC address. Later pings succeeded.

## Files
- topology.pkt: Packet Tracer file
- screenshots/: evidence of each step
