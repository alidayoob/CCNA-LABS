R1#SHOW RUNN
Building configuration...

Current configuration : 827 bytes
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
ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2911/K9 sn FTX1524W961-
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
 description ##SW1 ENGINEERING##
 ip address 10.0.0.62 255.255.255.192
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 description ##SW1 HR##
 ip address 10.0.0.126 255.255.255.192
 duplex auto
 speed auto
!
interface GigabitEthernet0/2
 description ##SW1 SALES##
 ip address 10.0.0.190 255.255.255.192
 duplex auto
 speed auto
!
interface Vlan1
 no ip address
 shutdown
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