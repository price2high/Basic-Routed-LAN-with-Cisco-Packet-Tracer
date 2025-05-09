```
enable
configure terminal
hostname Switch0
banner motd # Unauthorized access is prohibited. Disconnect immediately. #
enable secret Sw1tch0Secret!
service password-encryption
ip domain-name emilab.local
ip name-server 8.8.8.8
ip domain-lookup
clock timezone EST -5

interface vlan 1
 ip address 192.168.1.100 255.255.255.0
 no shutdown
exit

ip default-gateway 192.168.1.1

line console 0
 password c0nsol3Sw0
 login
 logging synchronous
exit

line vty 0 4
 password vtySw0Pass
 login
 transport input all
exit

interface range fa0/10 - 24
 shutdown
exit

end
copy running-config startup-config
```
