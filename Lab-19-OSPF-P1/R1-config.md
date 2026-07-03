R1#show running-config 
Building configuration...

Current configuration : 940 bytes
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
 duplex auto
 speed auto
!
interface FastEthernet1/0
 ip address 10.0.13.1 255.255.255.252
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
!
router ospf 1
 log-adjacency-changes
 network 10.0.12.1 0.0.0.0 area 0
 network 10.0.13.1 0.0.0.0 area 0
 network 1.1.1.1 0.0.0.0 area 0
 default-information originate
!
ip classless
ip route 0.0.0.0 0.0.0.0 GigabitEthernet3/0 
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