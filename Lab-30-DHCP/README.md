# Lab 30 - DHCP

## Objective
Configure DHCP pools on R2 for multiple subnets, set up R1 as a
DHCP client and relay agent, and verify address assignment from PCs.

## Topology
![Lab Topology](topology.png)

## Commands Used

### DHCP Pools on R2

**POOL1 - 192.168.1.0/24**
R2(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.10
R2(config)# ip dhcp pool POOL1
R2(dhcp-config)# network 192.168.1.0 255.255.255.0
R2(dhcp-config)# dns-server 8.8.8.8
R2(dhcp-config)# domain-name jeremysitlab.com
R2(dhcp-config)# default-router 192.168.1.1

**POOL2 - 192.168.2.0/24**
R2(config)# ip dhcp excluded-address 192.168.2.1 192.168.2.10
R2(config)# ip dhcp pool POOL2
R2(dhcp-config)# network 192.168.2.0 255.255.255.0
R2(dhcp-config)# dns-server 8.8.8.8
R2(dhcp-config)# domain-name jeremysitlab.com
R2(dhcp-config)# default-router 192.168.2.1

**POOL3 - 203.0.113.0/30**
R2(config)# ip dhcp excluded-address 203.0.113.1
R2(config)# ip dhcp pool POOL3
R2(dhcp-config)# network 203.0.113.0 255.255.255.252

### Step 2 - R1 G0/0 as DHCP Client
R1(config)# interface gigabitethernet0/0
R1(config-if)# ip address dhcp
R1(config-if)# no shutdown

**Result:** R1 received IP **203.0.113.2/30** from POOL3, address determined by DHCP.

### Step 3 - R1 as DHCP Relay Agent
R1(config)# interface gigabitethernet0/1
R1(config-if)# ip helper-address 203.0.113.1

### Step 4 - Request IP on PCs
PC1> ipconfig /release
PC1> ipconfig /renew

PC2> ipconfig /release
PC2> ipconfig /renew

### Verification
R2# show ip dhcp binding
R1# show ip interface gigabitethernet0/0
PC1> ipconfig /all

## Key Concepts Learned
- DHCP pools assign IP, DNS, domain name, and gateway automatically
- 'ip dhcp excluded-address' reserves addresses from the pool (e.g., for static devices)
- A router interface can act as a DHCP client with 'ip address dhcp'
- DHCP requests are broadcast (Layer 2) and don't cross routers by default
- 'ip helper-address' relays DHCP broadcasts as unicast to a remote DHCP server
- DHCP relay is required when the DHCP server is on a different subnet than the client

## Connectivity Test
- R1 G0/0 received IP from DHCP: ✅ 203.0.113.2/30
- PC1 received IP via DHCP relay: ✅ Success
- PC2 received IP via DHCP relay: ✅ Success

## Status
✅ Completed

## Notes
Part of Jeremy's IT Lab CCNA course 