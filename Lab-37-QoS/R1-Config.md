R1#show running-config 
Building configuration...

Current configuration : 1106 bytes
!
version 15.4
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
ip cef
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
spanning-tree mode pvst
!
class-map match-all HTTPS_MAP
 match protocol https
class-map match-all HTTP_MAP
 match protocol http
class-map match-all ICMP_MAP
 match protocol icmp
!
policy-map G0/0/0_OUT
 class HTTPS_MAP
  priority percent 10
  set ip dscp af31
 class HTTP_MAP
  bandwidth percent 10
  set ip dscp af32
 class ICMP_MAP
  bandwidth percent 5
  set ip dscp cs2
!
!
!
!
!
interface GigabitEthernet0/0/0
 ip address 172.16.0.1 255.255.255.252
 service-policy output G0/0/0_OUT
 duplex auto
 speed auto
!
interface GigabitEthernet0/0/1
 ip address 192.168.0.1 255.255.255.0
 duplex auto
 speed auto
!
interface GigabitEthernet0/0/2
 media-type sfp
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Vlan1
 no ip address
 shutdown
!
ip classless
ip route 0.0.0.0 0.0.0.0 172.16.0.2 
!
ip flow-export version 9
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