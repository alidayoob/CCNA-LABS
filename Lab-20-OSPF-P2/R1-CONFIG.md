R1#write
Building configuration...
[OK]
R1#show runn
Building configuration...

Current configuration : 855 bytes
!
version 12.2
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname R1
!
!
!
!
!
!
!
!
no ip cef
no ipv6 cef
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
!
!
!
!
!
!
!
interface Loopback1
 ip address 1.1.1.1 255.255.255.255
!
interface GigabitEthernet0/0
 ip address 10.0.12.1 255.255.255.252
 ip ospf 1 area 0
 duplex auto
 speed auto
!
interface FastEthernet1/0
 ip address 10.0.13.1 255.255.255.252
 ip ospf 1 area 0
 duplex auto
 speed auto
!
interface FastEthernet2/0
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface GigabitEthernet3/0
 ip address 203.0.113.1 255.255.255.252
 ip ospf 1 area 0
!
router ospf 1
 log-adjacency-changes
 auto-cost reference-bandwidth 10000
!
ip classless
!
ip flow-export version 9
!
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


R1#