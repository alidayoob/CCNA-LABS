R1-Config 
Using 1078 bytes
!
version 15.3
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname R1
!
!
boot system flash c2900-universalk9-mz.SPA.155-3.M4a.bin 
!
!
!
ip dhcp pool POOL1
 network 10.0.0.0 255.255.255.0
 default-router 10.0.0.254
!
!
!
ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2911/K9 sn FTX15243GX0-
license boot module c2900 technology-package FoundationSuiteK9
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
interface GigabitEthernet0/0
 ip address 192.168.12.1 255.255.255.0
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 ip address 10.0.0.254 255.255.255.0
 duplex auto
 speed auto
!
interface GigabitEthernet0/2
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Vlan1
 no ip address
 shutdown
!
router ospf 1
 log-adjacency-changes
 passive-interface GigabitEthernet0/1
 network 10.0.0.0 0.0.0.255 area 0
 network 192.168.12.0 0.0.0.255 area 0
!
ip classless
!
ip flow-export version 9
!
!
!
no cdp run
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


R1#