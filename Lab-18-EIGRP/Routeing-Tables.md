R1 routeing Table 
R1#show ip route eigrp
     2.0.0.0/32 is subnetted, 1 subnets
D       2.2.2.2 [90/130816] via 10.0.12.2, 00:58:21, GigabitEthernet0/0
     3.0.0.0/32 is subnetted, 1 subnets
D       3.3.3.3 [90/156160] via 10.0.13.2, 01:02:06, FastEthernet1/0
     4.0.0.0/32 is subnetted, 1 subnets
D       4.4.4.4 [90/156416] via 10.0.12.2, 00:48:35, GigabitEthernet0/0
     10.0.0.0/30 is subnetted, 4 subnets
D       10.0.24.0 [90/28416] via 10.0.12.2, 00:48:36, GigabitEthernet0/0
D       10.0.34.0 [90/30720] via 10.0.13.2, 01:02:33, FastEthernet1/0
D    192.168.4.0/24 [90/28672] via 10.0.12.2, 00:48:35, GigabitEthernet0/0
--------------------------------------------------------------------------------
R2 routeing Table:
R2#      show ip route eigrp
     1.0.0.0/32 is subnetted, 1 subnets
D       1.1.1.1 [90/130816] via 10.0.12.1, 01:01:44, GigabitEthernet0/0
     3.0.0.0/32 is subnetted, 1 subnets
D       3.3.3.3 [90/156416] via 10.0.12.1, 01:01:44, GigabitEthernet0/0
     4.0.0.0/32 is subnetted, 1 subnets
D       4.4.4.4 [90/156160] via 10.0.24.2, 00:50:14, FastEthernet1/0
     10.0.0.0/30 is subnetted, 4 subnets
D       10.0.13.0 [90/28416] via 10.0.12.1, 01:01:44, GigabitEthernet0/0
D       10.0.34.0 [90/30720] via 10.0.24.2, 00:50:14, FastEthernet1/0
D    192.168.4.0/24 [90/28416] via 10.0.24.2, 00:50:14, FastEthernet1/0

R2#
---------------------------------------------------------------------------------
R3 routeing Table:
R3#show ip route eigrp
     1.0.0.0/32 is subnetted, 1 subnets
D       1.1.1.1 [90/156160] via 10.0.13.1, 01:05:05, FastEthernet1/0
     2.0.0.0/32 is subnetted, 1 subnets
D       2.2.2.2 [90/156416] via 10.0.13.1, 01:00:45, FastEthernet1/0
     4.0.0.0/32 is subnetted, 1 subnets
D       4.4.4.4 [90/156160] via 10.0.34.2, 01:04:56, FastEthernet2/0
     10.0.0.0/30 is subnetted, 4 subnets
D       10.0.12.0 [90/28416] via 10.0.13.1, 01:02:30, FastEthernet1/0
D       10.0.24.0 [90/30720] via 10.0.34.2, 00:51:00, FastEthernet2/0
D    192.168.4.0/24 [90/28416] via 10.0.34.2, 01:04:56, FastEthernet2/0

R3#
-----------------------------------------------------------------------------------
R4 routeing Table:
R4#
R4#show ip route eigrp
     1.0.0.0/32 is subnetted, 1 subnets
D       1.1.1.1 [90/156416] via 10.0.24.1, 00:51:46, FastEthernet1/0
     2.0.0.0/32 is subnetted, 1 subnets
D       2.2.2.2 [90/156160] via 10.0.24.1, 00:51:46, FastEthernet1/0
     3.0.0.0/32 is subnetted, 1 subnets
D       3.3.3.3 [90/156160] via 10.0.34.1, 01:05:17, FastEthernet2/0
     10.0.0.0/30 is subnetted, 4 subnets
D       10.0.12.0 [90/28416] via 10.0.24.1, 00:51:46, FastEthernet1/0
D       10.0.13.0 [90/30720] via 10.0.34.1, 01:05:43, FastEthernet2/0

R4#
------------------------------------------------------------------------------------