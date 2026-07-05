R2#show start
Using 779 bytes
!
version 12.2
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
 ip address 2.2.2.2 255.255.255.255
!
interface GigabitEthernet0/0
 ip address 10.0.12.2 255.255.255.252
 ip ospf 1 area 0
 duplex auto
 speed auto
!
interface FastEthernet1/0
 ip address 10.0.24.1 255.255.255.252
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
no cdp run
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