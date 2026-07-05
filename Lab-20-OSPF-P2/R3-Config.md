R3#write
Building configuration...
[OK]
R3#show star
Using 766 bytes
!
version 12.2
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname R3
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
 ip address 3.3.3.3 255.255.255.255
!
interface GigabitEthernet0/0
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface FastEthernet1/0
 ip address 10.0.13.2 255.255.255.252
 ip ospf 1 area 0
 duplex auto
 speed auto
!
interface FastEthernet2/0
 ip address 10.0.34.1 255.255.255.252
 ip ospf 1 area 0
 duplex auto
 speed auto
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


R3#