R2#show startup-config 
Using 1287 bytes
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
no ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2911/K9 sn FTX1524YNKY-
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
 ip address 192.168.1.254 255.255.255.0
 ip ospf 1 area 0
 ip access-group ALI2 out
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 ip address 192.168.2.254 255.255.255.0
 ip ospf 1 area 0
 ip access-group ALI1 out
 duplex auto
 speed auto
!
interface GigabitEthernet0/2
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Serial0/0/0
 ip address 203.0.113.2 255.255.255.252
 ip ospf 1 area 0
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
router ospf 1
 log-adjacency-changes
 passive-interface GigabitEthernet0/0
 passive-interface GigabitEthernet0/1
!
ip classless
!
ip flow-export version 9
!
!
ip access-list standard ALI2
 permit host 172.16.1.1
 permit host 172.16.2.1
 deny 172.16.1.0 0.0.0.255
 deny 172.16.2.0 0.0.0.255
 permit any
ip access-list standard ALI1
 deny 172.16.2.0 0.0.0.255
 permit any
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