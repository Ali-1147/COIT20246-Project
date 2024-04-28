# Network Design
This section gives the detailed network design.

[Network Design Diagrams and Justifications](#network-design-diagrams-and-justifications) | [WiFi Design](#wifi-design) | [Address Allocations](#address-allocations) | [Recommended Hardware](#recommended-hardware) | [Plan](./plan.md) | [Cloud Services](./cloud.md) | [Security](./security.md) | [Ethics](./ethics.md) | [Reflection](./reflection.md) | [Return to index](./README.md)

## Network Design Diagrams and Justifications
- Core Switching and Routing:
Implement a robust core switching and routing infrastructure to handle the traffic between different geographical locations and provide connectivity to the internet.
Use high-performance switches with sufficient port density and layer 3 routing capabilities to support the network traffic.
Employ redundant core switches for high availability and fault tolerance.
- Distribution Switches:
Deploy distribution switches at each geographical location to aggregate the traffic from access switches and provide connectivity to the core switches.
Use stackable switches for scalability and ease of management.
Ensure sufficient uplink capacity to connect to the core switches.
- Access Switches:
Install access switches in each office or building to connect end-user devices, IP cameras, and other peripherals.
Utilize Power over Ethernet (PoE) switches to power IP cameras and wireless access points.
Implement VLANs to logically segment the network and improve security and performance.
- Wireless Network:
Deploy wireless access points (WAPs) throughout each office or building to provide wireless connectivity to users and customers.
Use enterprise-grade WAPs that support the latest Wi-Fi standards for optimal performance and security.
Implement a secure authentication mechanism such as WPA2-Enterprise or 802.1X for user authentication.
- Internet Connectivity:
Establish redundant internet connections with failover capabilities to ensure continuous internet access for users and customers.
Implement firewalls and intrusion prevention systems (IPS) to protect against cyber threats and unauthorized access.
Consider implementing content filtering to restrict access to inappropriate websites and improve network security.
- VPN Connectivity:
Set up virtual private network (VPN) connections between different geographical locations to securely connect remote offices and users.
Use VPN encryption protocols such as IPSec or SSL/TLS to protect data transmitted over the VPN connections.
- Data Center:
Design and build a dedicated data center to host servers, including the web server and other critical applications.
Implement redundant power supplies, cooling systems, and network connectivity to ensure high availability and reliability.
Utilize server virtualization technology to optimize resource utilization and simplify management.
- Monitoring and Management:
Deploy network monitoring tools to continuously monitor the health and performance of the network infrastructure.
Implement network management systems for centralized configuration, monitoring, and troubleshooting.
Regularly update and patch network devices to address security vulnerabilities and ensure compliance with industry standards.

## WiFi Design
Network Devices:
•	Wireless Router/Access Point (AP): We will need multiple access points (APs) strategically placed throughout the office to provide sufficient coverage and signal strength. Aim for high-quality business-grade routers/APs that can handle high user density.
•	Network Switches: Gigabit Ethernet switches are essential for connecting your APs, wired devices, and the internet connection.
WiFi Settings:
•	SSID (Network Name): Create a unique and easily identifiable SSID for your business network. Avoid using generic names like "WiFi" or "Linksys."
•	Password: Implement a strong WPA2-PSK (AES) encryption with a complex password. Avoid using easily guessable passwords or sharing them openly. Consider a password management solution for secure distribution.
•	Frequency Band: Utilize both 5 GHz and 2.4 GHz bands. The 5 GHz band offers faster speeds but shorter range, while 2.4 GHz offers better range but is more susceptible to interference from other devices. Enable band steering on your APs to automatically direct devices to the optimal band.
•	Channel Selection: Use WiFi analyzer tools to identify the least congested channels in your area and configure your APs to broadcast on those channels. This minimizes interference from other WiFi networks.
•	Client Isolation: Enable client isolation to prevent wireless devices from communicating directly with each other on the network, enhancing security.
•	Guest Network (Optional): Consider setting up a separate guest network with limited access for visitors. This keeps your main network secure.
•	Transmit Power: Adjust the transmit power of your APs to optimize coverage without creating unnecessary signal overlap.
Additional Considerations:
•	Placement of Access Points: Conduct a site survey to determine the optimal placement of APs for even signal distribution and to minimize dead zones. Consider factors like office layout, building materials, and potential interference.
•	Network Management: Invest in a network management system to monitor network performance, identify and troubleshoot issues, and manage access points centrally.
•	Scalability: Choose equipment that can be easily scaled up as your business grows and the number of users increases

## List of Recommended Hradware
- Essential Hardware:
- Multiple Wireless Access Points (APs):
•	models with features like band steering, MU-MIMO (for better multi-user performance), and mesh capabilities for seamless coverage.
•	Gigabit Ethernet Switches: one or more Gigabit Ethernet switches depending on the number of wired devices and APs. Choose a switch with enough ports to accommodate your current and future needs.
•	Ethernet Cables: Cat5e or Cat6 Ethernet cables are recommended for reliable wired connections between your devices, switches, and APs.
- Optional Hardware:
•	Wireless Router (if not integrated with your APs): A separate router to connect yur network to the internet service provider (ISP).
•	Network Management System: This is software that helps to monitor network performance, troubleshoot issues, and manage your APs centrally. While not essential, it simplifies network management for larger deployments.
- Additional Considerations:
•	PoE (Power over Ethernet) Switches: If we chosen APs support PoE, we can eliminate the need for separate power outlets for each AP. PoE delivers power over the same Ethernet cable used for data transmission.
•	Patch Panel (Optional): A patch panel helps organize network cables in a rack-mounted setup, improving aesthetics and manageability (especially for larger deployments).

- Cisco WS-C2960X-24PS-L Catalyst 2960-X 24 GigE PoE 370W 4 x 1GB SFP
SKU: WS-C2960X-24PS-L

Links:

https://www.xsnet.com.au/product/cisco/20927/ws-c2960x-24ps-l

https://www.thetelecomshop.com/au/networking

https://www.xsnet.com.au/

## Address Allocations
Class A Public & Private IP Address Range
Class A addresses are for networks with large number of total hosts. Class A allows for 126 networks by using the first octet for the network ID. The first bit in this octet, is always zero. The remaining seven bits in this octet complete the network ID. The 24 bits in the remaining three octets represent the hosts ID and allows for approximately 17 million hosts per network. Class A network number values begin at 1 and end at 127.
Group member ID: Vansh Patel: 12264208
IP range starts with 08.
•	Public IP Range: 8.16.0.0 to 127.16.0.0
o	First octet value range from 8 to 127
 	Public IP Range	Private IP Range	Subnet Mask	# of Networks	# of Hosts per Network
Class A	8.16.0.0 to	18.16.0.0 to	255.0.0.0 	126	16,777,214
	127.16.0.0	10.255.255.255			

DATA-RouterA: 90.44.22.5	MAIN-WAP2E: 8.16.0.19
MAIN-RouterA: 90.44.22.6	MAIN-WAP3A: 8.16.0.20
Primary Server: 8.16.0.1	MAIN-WAP3B: 8.16.0.21
Backup Server: 172.16.0.2	MAIN-WAP3C: 8.16.0.22
DATA-Switch1: 8.16.0.3	MAIN-WAP3D: 8.16.0.23
MAIN-Switch1: 8.16.0.4	MAIN-WAP3E: 8.16.0.24
MAIN-Switch2: 8.16.0.5	MAIN-WAP4A: 8.16.0.25
MAIN-Switch3: 8.16.0.6	MAIN-WAP4B: 8.16.0.26
MAIN-Switch4: 8.16.0.7	MAIN-WAP4C: 8.16.0.27
DATA-P2PWAP: 8.16.0.8	MAIN-WAP4D: 8.16.0.28
MAIN-P2PWAP: 8.16.0.9	MAIN-WAP4E: 8.16.0.29
MAIN-WAP1A: 8.16.0.10	Filing System: 8.16.0.30
MAIN-WAP1B: 8.16.0.11	DHCP: 8.16.0.31
MAIN-WAP1C: 8.16.0.12	Exchange Server: 8.16.0.32
MAIN-WAP1D: 8.16.0.13	DATAPRINTER1: 8.16.0.33
MAIN-WAP1E: 8.16.0.14	MAINPRINTER1: 8.16.0.34
MAIN-WAP2A: 8.16.0.15	MAINPRINTER2: 8.16.0.35
MAIN-WAP2B: 8.16.0.16	MAINPRINTER3: 8.16.0.36
MAIN-WAP2C: 8.16.0.17	MAINPRINTER4: 8.16.0.37
MAIN-WAP2D: 8.16.0.18	

- The rest of the IPs, ranging from 8.16.0.37 to 8.16.1.254, will allow up to four hundred and seventy-three dynamic IPs left for connecting hosts on the network for use.  These will be designated to the two hundred wireless users, twenty-five wired workstations, and other devices connected to the network.

## Recommended Hardware
