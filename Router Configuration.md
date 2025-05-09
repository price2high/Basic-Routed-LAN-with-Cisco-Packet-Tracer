### ⚙️ Router Configuration (R1):

```bash
enable
configure terminal
hostname R1
banner motd # Unauthorized access is prohibited. #
enable secret ClassC0nfig!
service password-encryption
ip domain-name emilab.local
ip name-server 8.8.8.8
ip domain-lookup
clock timezone EST -5

interface g0/0
 description Connected to Switch0
 ip address 192.168.1.1 255.255.255.0
 no shutdown
exit

interface g0/1
 description Connected to Switch1
 ip address 192.168.2.1 255.255.255.0
 no shutdown
exit

line console 0
 password c0nsol3Pass
 login
 logging synchronous
exit

line vty 0 4
 password vtyPa55word
 login
 transport input all
exit

end
copy running-config startup-config
```
