Using 809 bytes
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
 duplex auto
 speed auto
!
interface FastEthernet2/0
 ip address 10.0.34.1 255.255.255.252
 duplex auto
 speed auto
!
router eigrp 1
 passive-interface Loopback1
 network 10.0.13.2 0.0.0.0
 network 10.0.34.1 0.0.0.0
 network 3.3.3.3 0.0.0.0
 no auto-summary
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