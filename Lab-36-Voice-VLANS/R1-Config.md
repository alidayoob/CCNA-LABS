R1#show running-config 
Building configuration...

Current configuration : 1237 bytes
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
ip dhcp excluded-address 192.168.20.1 192.168.20.10
!
ip dhcp pool VOICE
 network 192.168.20.0 255.255.255.0
 default-router 192.168.20.1
 option 150 ip 192.168.20.1
!
!
!
ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2811/K9 sn FTX1017C35F-
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
interface FastEthernet0/0
 no ip address
 duplex auto
 speed auto
!
interface FastEthernet0/0.1
 encapsulation dot1Q 10
 no ip address
!
interface FastEthernet0/0.2
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
!
interface FastEthernet0/1
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
!
ip flow-export version 9
!
!
!
!
!
!
!
telephony-service
 max-ephones 2
 max-dn 2
 ip source-address 192.168.20.1 port 2000
!
ephone-dn 1
 number 2010
!
ephone-dn 2
 number 2020
!
ephone 1
 device-security-mode none
 mac-address 0001.437B.4124
 type 7960
 button 1:1
!
ephone 2
 device-security-mode none
 mac-address 00D0.D357.40D9
 type 7960
 button 1:2
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