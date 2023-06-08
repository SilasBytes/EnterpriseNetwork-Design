# 3 Tier Network Architecture
This is an enterprise network for a mid-size organization with a core, distribution, and access layer that I designed and emulated using Cisco Packet Tracer.

Enterprise network design of a main site and a secondary site interconnected.
![enterprisenetwork](https://github.com/SilasBytes/EnterpriseNetwork-Design/assets/135275768/4f6ef1a3-74b5-4008-b3fe-216fb92019be)
![image](https://github.com/SilasBytes/EnterpriseNetwork-Design/assets/135275768/12ed76c0-0e86-4380-9e6e-ac775d6055e7)


Main site's network consists of the DMZ, Data center, and enterprise users.
The secondary site's network consists of enterprise users.

Routing Protocols: BGP was used to route between the main and secondary sites. Each site uses OSPF internally to route between different networks and OSPF routes were redistributed to BGP to connect the sites' networks.

Firewall was configured in Cisco's ASA with zone-based security: DMZ, Data Center, Users, WAN, and Site2WAN. Ingress traffic entering DMZ, Data Center, and Users would be inspected and either discarded or permitted by the policies. Egress traffic is allowed between the Users in any zones.

IPsec tunnel was configured site to site to allowed a secure VPN tunnel between the sites.

VoIP was configured using Cisco IOS Telephony Service and IP addresses are assigned by the VoIP's gateway.

Wireless Lan Controller was configured to manage the Access Points's configuration and provide wifi using WPA2's Enterprise mode.

