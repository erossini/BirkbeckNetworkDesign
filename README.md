# Network Design

A computer network needs to be designed and simulated using Cisco Packet Tracer for a medium sized business that has three sites, London, Birmingham and Manchester. Each site requires 802.11 wireless access for their users (staff, guests) and IP Telephony. The wireless network should allow for up to 100 guest users. The specific requirements of the network by site are as follows:

| Site | Users | Network services | Departments |
| --- | --- | --- | --- |
| London | 150 | DNS, DHCP, SYSLOG, HTTPS, Local DNS, AAA, NAT | HR, Sales, Marketing, Finance, IT |
| Birmingham | 50 | DHCP, SYSLOG, AAA, NAT | R&D, Customer Service |
| Manchester | 100 | DHCP, SYSLOG, AAA, NAT | Operations, Manufacturing, Quality Control, Logistics |

A public IP address block **192.0.2.0/24** is available for the purpose of the WAN connections.

1. Design an IPv4 addressing scheme suitable for the whole network. You must include the internal private addresses as well as the required public addresses. Show where these addresses could be used in the form of a table showing the name of the network segment and the ip address range. It may be useful to sketch out a logical topology diagram for the whole network and identify each of the subnets and their sizes before calculating the required subnets.
2. Design a logical topology for the London LAN only (no need for others) using Cisco Packet Tracer version 8.2.2. You do not need to show all the end user devices (two will suffice), however you must include all the necessary network segments, infrastructure devices, servers and security devices. Configure host addresses, routing and switching. You are not expected to configure any security devices, other than to implement basic routing to pass packets through. Finally, test your network for reachability using the ping command.
3. Describe how you would connect the three sites together cost effectively in order to form a WAN. You may show the connections in the form of a logical topology diagram. Explain your chosen WAN technology stating the possible bandwidths and expected throughput.

For this part you need to include a table showing the addressing scheme, Cisco Packet Tracer simulation (.pkt file) and a topology diagram showing the WAN connections, each supported by brief explanations and screenshots where necessary.

### Key points

- The `DMZ` is located in the London office and contains the web servers, mail servers and so on. In the `DMZ` the IP class is `172.16.1.0/24`.
- Each site has to use a specific range of IPs like for example:
  
  | Site                 | IP Range      |
  |----------------------|---------------|
  | London (Server Farm) | 10.0.0.0/24   |
  | London               | 10.50.0.0/24  |
  | Birmingham           | 10.100.0.0/24 |
  | Manchester           | 10.150.0.0/24 |

- The server farm with the internal server, such as File Server or SQL Server, is located in the London office but the other offices can access them
- Add the appropriate VLAN (for example for the departments). Avoid using VLAN 1 or 99.
- Configuration of the wireless is required
- Redundancy is required wherever is possible and necessary

## Example of IP table

| Device     | Interface    | IP Address      | Subnet Mask     | Default Gateway |
|------------|--------------|-----------------|-----------------|-----------------|
| R1         | G0/0         | 209.165.200.225 | 255.255.255.248 | N/A             |
|            | S0/0/0 (DCE) | 10.1.1.1        | 255.255.255.252 |                 |
| R2         | S0/0/0       | 10.1.1.2        | 255.255.255.252 | N/A             |
|            | S0/0/1 (DCE) | 10.2.2.2        | 255.255.255.252 |                 |
| R3         | G0/1         | 172.16.3.1      | 255.255.255.0   | N/A             |
|            | S0/0/1       | 10.2.2.1        | 255.255.255.252 |                 |
| ASA        | G1/1         | 209.165.200.226 | 255.255.255.248 | N/A             |
|            | G1/2         | 192.168.1.1     | 255.255.255.0   |                 |
|            | G1/3         | 192.168.2.1     | 255.255.255.0   |                 |
| DMZ Server | NIC          | 192.168.2.3     | 255.255.255.0   | 192.168.2.1     |
| PC-B       | NIC          | 192.168.1.3     | 255.255.255.0   | 192.168.1.1     |
| PC-C       | NIC          | 172.16.3.3      | 255.255.255.0   | 172.16.3.1      |

## Network example

![image](https://github.com/user-attachments/assets/ce914d48-77a9-47cc-89fd-22b8910f3e74)


<img width="1421" alt="Network Design" src="https://github.com/user-attachments/assets/a054f66c-2612-4f22-821e-4f8b049b4cee" />


