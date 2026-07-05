R4#show startup-config 
Using 915 bytes
!
version 12.2
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname R4
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
 ip address 4.4.4.4 255.255.255.255
!
interface GigabitEthernet0/0
 ip address 192.168.4.254 255.255.255.0
 ip ospf 1 area 0
 duplex auto
 speed auto
!
interface FastEthernet1/0
 ip address 10.0.24.2 255.255.255.252
 ip ospf 1 area 0
 duplex auto
 speed auto
!
interface FastEthernet2/0
 ip address 10.0.34.2 255.255.255.252
 ip ospf 1 area 0
 duplex auto
 speed auto
!
router ospf 1
 log-adjacency-changes
 passive-interface default
 no passive-interface FastEthernet1/0
 no passive-interface FastEthernet2/0
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


R4#