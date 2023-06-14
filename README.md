# 3 Tier Network Architecture
This is an enterprise network for a mid-size organization with a core, distribution, and access layer that I designed and emulated using Cisco Packet Tracer.

Main site's network consists of the DMZ, Data center, and enterprise users.
The secondary site's network consists of enterprise users.

![enterprisenetwork](https://github.com/SilasBytes/EnterpriseNetwork-Design/assets/135275768/4f6ef1a3-74b5-4008-b3fe-216fb92019be)
![image](https://github.com/SilasBytes/EnterpriseNetwork-Design/assets/135275768/12ed76c0-0e86-4380-9e6e-ac775d6055e7)

## Routing Protocols
BGP was used to route between the main and secondary sites. Each site uses OSPF internally to route between different networks and the OSPF routes were redistributed to BGP to connect the sites' networks.

Main site use multiarea OSPF, with the users network in area 1, data center in area 2, the core switches in area 0.
![networkprotodiagram](https://github.com/SilasBytes/EnterpriseNetwork-Design/assets/135275768/2943bf8e-4182-4661-8dc8-11d12eb95102)

## Security
Firewall was configured in Cisco's ASA with zone-based security in the Main Site: DMZ, Data Center, Users, Internet, and Site2WAN. 

Data Center, Users, and Site2WAN have been configured with a security level of 100 while DMZ zone is set to 50 and Internet zone is set to 0.

IPsec tunnel was configured site to site to allowed a secure VPN tunnel between the sites using IKEv1 and pre-shared key.

## VoIP
VoIP was configured using Cisco IOS Telephony Service and IP addresses are assigned via DHCP by the VoIP's gateway.

## Wifi
Wireless Lan Controller was configured to manage the Access Points' configurations and provide Wifi using WPA2's Enterprise mode. Authencation is done using a RADIUS server that authenticates users connecting to the site's wifi.

