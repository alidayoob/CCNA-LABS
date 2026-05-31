# Lab 05 - Ethernet LAN Switching

## Objective
Understand how switches learn MAC addresses and how ARP works
by analyzing network traffic in simulation mode.

## Topology
![Lab Topology](topology.png)

## What I Did

### Step 1 - Analysis Before Ping
With empty MAC and ARP tables, sending a ping from PC1 to PC3 generates:
- ARP Request (Broadcast) from PC1 to find PC3's MAC address
- All devices on the network receive the ARP broadcast
- Only PC3 replies with ARP Reply (Unicast)
- After ARP, ICMP Echo (ping) is sent from PC1 to PC3

### Step 2 - Simulation Mode Verification
- Used Packet Tracer simulation mode to observe traffic flow
- Verified ARP broadcast reached all devices
- Confirmed switches learned MAC addresses from incoming frames

### Step 3 - MAC Address Table Learning
- Sent pings between all PCs to generate traffic
- Switches learned MAC addresses of all PCs dynamically

### Step 4 - Show Commands Used
SW1# show mac address-table
SW2# show mac address-table
### Step 5 - Clear MAC Address Table
SW1# clear mac address-table dynamic
SW2# clear mac address-table dynamic

## Key Concepts Learned
- Switches learn MAC addresses from the SOURCE of incoming frames
- Unknown unicast frames are flooded like broadcasts
- ARP is used to resolve IP addresses to MAC addresses
- Dynamic MAC entries can be cleared manually

## Status
✅ Completed

## Notes
Part of Jeremy's IT Lab CCNA course