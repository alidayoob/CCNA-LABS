R2#show running-config 
Building configuration...

Current configuration : 1116 bytes
!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname R2
!
!
!
!
!
!
!
!
ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2911/K9 sn FTX1524H9Q0-
!
!
!
!
!
!
!
!
!
!
!
!
!
spanning-tree mode pvst
!
!
!
!
!
!
interface Tunnel10
 ip address 192.168.1.2 255.255.255.252
 mtu 1476
 tunnel source GigabitEthernet0/0/0
 tunnel destination 100.0.0.2
!
!
interface GigabitEthernet0/0
 ip address 10.0.2.1 255.255.255.0
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface GigabitEthernet0/2
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface GigabitEthernet0/0/0
 ip address 200.0.0.2 255.255.255.252
!
interface Vlan1
 no ip address
 shutdown
!
router ospf 1
 log-adjacency-changes
 passive-interface GigabitEthernet0/0
 network 192.168.1.0 0.0.0.255 area 0
 network 10.0.2.0 0.0.0.255 area 0
!
ip classless
ip route 100.0.0.2 255.255.255.255 GigabitEthernet0/0/0 
!
ip flow-export version 9
!
!
!
!
!
!
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
!
!
end


R2# 