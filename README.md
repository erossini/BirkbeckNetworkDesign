# Network Design

A computer network needs to be designed and simulated using Cisco Packet Tracer for a medium sized business that has three sites, London, Birmingham and Manchester. Each site requires 802.11 wireless access for their users (staff, guests) and IP Telephony. The wireless network should allow for up to 100 guest users. The specific requirements of the network by site are as follows:

| Site | Users | Network services | Departments |
| --- | --- | --- | --- |
| London | 150 | DNS, DHCP, SYSLOG, HTTPS, Local DNS, AAA, NAT | HR, Sales, Marketing, Finance, IT |
| Birmingham | 50 | DHCP, SYSLOG, AAA, NAT | R&D, Customer Service |
| Manchester | 100 | DHCP, SYSLOG, AAA, NAT | Operations, Manufacturing, Quality Control, Logistics |

A public IP address block **192.0.2.0/24** is available for the purpose of the WAN connections.

1. Design an IPv4 addressing scheme suitable for the whole network. You must include the internal private addresses as well as the required public addresses. Show where these addresses could be used in the form of a table showing the name of the network segment and the ip address range. It may be useful to sketch out a logical topology diagram for the whole network and identify each of the subnets and their sizes before calculating the required subnets.
2. Design a logical topology for the London LAN only (no need for others) using Cisco Packet Tracer version 8.2.2. You do not need to show all the end user devices (two will suffice), however you must include all the necessary network segments, infrastructure devices, servers and security devices. Redundancy is important. Configure host addresses, routing and switching. You are not expected to configure any security devices, other than to implement basic routing to pass packets through. Finally, test your network for reachability using the ping command.
3. Describe how you would connect the three sites together cost effectively in order to form a WAN. You may show the connections in the form of a logical topology diagram. Explain your chosen WAN technology stating the possible bandwidths and expected throughput.

For this part you need to include a table showing the addressing scheme, Cisco Packet Tracer simulation (.pkt file) and a topology diagram showing the WAN connections, each supported by brief explanations and screenshots where necessary.

## Network example

![image](https://github.com/user-attachments/assets/ce914d48-77a9-47cc-89fd-22b8910f3e74)
