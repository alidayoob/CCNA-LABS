R3#show startup-config 
Using 1056 bytes
!
version 15.1
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
ipv6 unicast-routing
!
no ipv6 cef
!
!
!
!
license udi pid CISCO2911/K9 sn FTX15245527-
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
 no ip address
 duplex auto
 speed auto
 ipv6 address 2001:DB8:0:3::1/64
 ipv6 address autoconfig
!
interface GigabitEthernet0/1
 no ip address
 duplex auto
 speed auto
 ipv6 address 2001:DB8:0:13::2/64
!
interface GigabitEthernet0/2
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Serial0/0/0
 no ip address
 ipv6 enable
!
interface Serial0/0/1
 no ip address
 clock rate 2000000
 shutdown
!
interface Vlan1
 no ip address
 shutdown
!
ip classless
!
ip flow-export version 9
!
ipv6 route 2001:DB8:0:1::/64 GigabitEthernet0/1 2001:DB8:0:13::1
ipv6 route 2001:DB8:0:1::/64 Serial0/0/0 FE80::20B:BEFF:FED7:4901 254
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


R3#