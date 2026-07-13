R1#show running-config 
Building configuration...

Current configuration : 1510 bytes
!
version 15.1
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
license udi pid CISCO2911/K9 sn FTX15245X2K-
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
ip name-server 192.168.1.100
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
 ip address 172.16.1.254 255.255.255.0
 ip access-group 102 in
 ip access-group 101 out
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 ip address 172.16.2.254 255.255.255.0
 ip access-group 103 in
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
 ip address 203.0.113.1 255.255.255.252
 clock rate 128000
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
 network 0.0.0.0 255.255.255.255 area 0
!
ip classless
!
ip flow-export version 9
!
!
access-list 101 deny ip 172.16.2.0 0.0.0.255 host 172.16.1.1
access-list 101 permit ip any any
access-list 102 deny tcp 172.16.1.0 0.0.0.255 host 192.168.1.100 eq domain
access-list 102 deny udp 172.16.1.0 0.0.0.255 host 192.168.1.100 eq domain
access-list 102 permit ip any any
access-list 103 deny tcp 172.16.2.0 0.0.0.255 host 192.168.2.100 eq www
access-list 103 deny tcp 172.16.2.0 0.0.0.255 host 192.168.2.100 eq 443
access-list 103 permit ip any any
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