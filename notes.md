# Network Security Systems & Architecture

## Devices

- Network Interface Card (NIC) - Enables interaction among devices over the network

- Switch                        - Layer 2 communication device (within a LAN)

- Router                        - Layer 3 communication device that connects networks

- Firewall                      - Hardware or software that filters traffic

- End Device                    - Source or destination network device

- Access Point                  - A device that provides a wireless network connection (WLAN)

- Intermediary devices          - Devices such as switches, routers, firewalls, and access points are intermediary devices. Intermediary devices are responsible for connecting
                                  end devices to the network and managing data flow.
                                  
                                  
## Virutal Local Area Networks (VLANs)

- VLANs are a popular concept implemented in most administrative networks. By default, all devices connected to a single switch belong to one broadcast domain.

- Switch - Switches can also extend broadcast domains. Each network/subnetwork represents a broadcast domain.

# Advantages of implementing VLANs

- Implementing VLANs on a network breaks a large broadcast domain into smaller broadcast domains.

- VLANs are logical channels rather than physical connections.

- VLANs logically group devices and enable devices on the same VLAN to communicate. Each port on a switch can belong to a VLAN. 

- VLANs can also serve as a security measure by separating network traffic.

# Risks on VLANs

- Default VLANs are pre-configured on all switches. VLAN 1 is the default VLAN and can pose a security risk.


## Access-Control Lists

- Access-control lists (ACLs) enable packet filtering in a network environment. 

- ACLs are rule-based security features used to filter packets based on various factors found in the packet header. Traffic can be filtered based on network address, protocol, port
numbers, and service. 

- By default, Layer 3 devices such as routers do not perform packet filtering, only routing. 

- ACLs are manually configured to enable packet filtering. 

- Access-control lists can be used for both IPv4 and IPv6 protocols.


## Redundancy 

- Network redundancy is critical to maintaining network reliability

- Virtual IP - A mechanism to provide redundancy among default gateway IP addresses is to implement a redundancy protocol on the network.

## Protocol Redundancy 

Open source:

- Common Address Redundancy Protocol (CARP)

- Virtual Router Redundancy Protocol (VRRP)

Proprietary:

- Hot Standby Router Protocol (HSRP)

- Gateway Load Balancing Protocol (GLBP)

- Fail-over cluster - A failover cluster is also known as a high-availability cluster. (p13)

## Load Balancers

- Hardware Load Balancers - Physical hardware equipment used to distribute traffic across multiple servers

- Software Load Balancers - Commercial or open-source applications installed on a server that functions similarly to hardware load balancers

- Virtual Load Balancers - A virtual load balancer mimics a software load balancer through virtualization. It runs the software of a physical load balancer on a virtual machine.

Implementing load balancing with a failure-resistant topology benefits the application, user, and organization. 

## DMZ 

- A demilitarized zone is an external-facing network. A DMZ is a method of protecting an internal network while providing public services, such as web-based services.

- A DMZ is the first station an external user encounters when accessing an organizational network. Sensitive services, such as storage, email, or mainframes, should never be placed in the DMZ due to their exposure to the internet. On the other hand, public web servers are often placed in DMZ networks.

## Forward Proxy vs. Reverse Proxy

- Forward Proxy - Forward proxies operate on the client-side. They can be used to bypass IP restrictions, maintain anonymity, and filter web traffic. 

- Reverse Proxy - Reverse proxies operate on the server-side. They can be used to mitigate DDoS attacks
and can act as web application firewalls.


## Network Security Systems 

- Firewall - A firewall is a Layer 3 device that monitors and controls incoming and outgoing traffic on a network. It also secures traffic between trusted and untrusted external networks.

- IPS & IDS - Intrusion protection systems (IPS) and intrusion detection systems (IDS) are security systems that work with predefined rules based on traffic analysis. These systems aim to prevent network attacks and vulnerabilities. 

- IPS can examine and block network traffic.

- IDS typically operates in tap mode (passive) but can also be placed inline (active mode).

- Web Application Firewall (WAF) - A web application firewall (WAF) filters and blocks unwanted HTTP or HTTPS traffic based on predefined rules to and from a web server.

- Common web attacks such as XSS (cross-site scripting) and SQLi (SQL injections) are examples of unwanted traffic blocked
by WAF.


# Secure Management Access 

- Authentication, Authorization, and Accounting (AAA) Concepts - The AAA protocol provides a scalable framework for implementing and ensuring network access security. Administrators can use this protocol to control who can access network resources and track or audit that access.

- What Does AAA Do?

- AAA is a model that describes how to:

- Authenticate user accounts.
- Control access to resources.
- Audit network activity.
- Ensure policy compliance.

- Local vs. Remote Authentication

- Local

- Manages each device individually
- Secures each device individually
- Configures users on each device individually

- Remote

- Central Management 
- Central Security 
- Central user configuration

## Two common AAA protocols are: (p27)

- Remote Authentication Dial-In User Service (RADIUS) 
- Developed as an open standard by the Internet Engineering Task Force (IETF)
- Uses Transport protocol UDP
- Combines authentication and authorization

- Terminal Access Controller Access-Control System Plus (TACACS+)
- Developed by Cisco
- Cisco’s latest AAA protocol version
- Uses Transport protocol TCP
- Separates authentication, authorization, and accounting processes

- RADIUS is also a common authentication protocol utilized by the 802.1X security protocol.
- Suitable for wired and wireless networks


# 802.1X Authentication

- 802.1X is a security protocol defined by the Institute of Electrical and Electronics Engineers (IEEE) standards organization. This security protocol authenticate new users and devices requesting access to the network. It can operate on wired or wireless LANs, campuses, and enterprise networks.

- 802.1X Components

There are three components of 802.1X:
- Supplicant - The client (workstation) receives credentials from a user and submits them to the authenticator. Workstations can be any PC operating system or component of a software application. The client must be running 802.1X-compliant software

- Authenticator - This device controls physical access to the network by acting as a proxy between the client (supplicant) and the authentication server. The authenticator relays credentials received from a supplicant to the authentication server and is typically an available network device, such as a switch or an access point.

- Authentication Server - This device validates credentials received from an authenticator. The authentication server determines the level of access in the network for an end-user or device. Cisco’s Secure Access Control System (ACS) supports two protocols, TACACS+ and RADIUS.


- EAP - Extensible Authentication Protocol (EAP) is an authentication framework that provides transport for request and response parameters.

- EAP over LAN (EAPOL) 

# Network Attacks & Mitigation

## MAC Spoofing

- Address Resolution Protocol (ARP) Poisoning - ARP poisoning is a common attack and is one of the many ways an On-Path attack maybe accomplished.
- ARP poisoning can enable an attacker to intercept traffic.
- Denial of Service (DoS): An attacker can perform a DoS attack by poisoning ARP tables and creating false traffic routes.
- Spoofing Identity: An attacker can use ARP Poisoning to hide in the network.

ARP Poisoning Protection
Various techniques to detect ARP poisoning include:
- Identify duplicate MAC addresses.
- Check for suspicious ARP traffic.
- Use static ARP entries.
- Configure port security.
- Use encrypted protocols.
- Prevent traffic interception and eavesdropping.

## CAM Table Overflow

- The MAC address table of a switch uses content-addressable memory (CAM) as the physical component to store MAC addresses. The CAM table has limited space for MAC
addresses due to the limitations of the switch. When the CAM table becomes flooded, the switch will operate in fail-open mode, during which it will behave like a hub.

- In this mode, it begins forwarding frames out of all switch ports. This fail-open mode can lead to a hacker capturing all traffic flowing through the switch.

## Port Security

- Port security operates at Layer 2 of the OSI model and is used to prevent unauthorized devices from accessing the network. Port security is not enabled by default on switch ports and requires manual configuration.

## VLAN Hopping 

- VLAN hopping occurs when a frame is sent to one VLAN but is believed to be in a different VLAN. Once VLAN hopping has occurred, the attacker bypasses switch restrictions and intercepts traffic from various VLANs.

- Switch Spoofing

- Switch Spoofing manipulates a proprietary Cisco protocol called Dynamic Trunking Protocol (DTP). DTP automatically creates trunk links between Cisco switches. DTP
messages between switches can unintentionally become spoofed and unintentionally cause the switch port to enter trunking mode. An attacker can introduce a rogue switch, enable trunking, and access all of the VLANs on the switch. This type of attack allows the attacker to send tagged VLAN traffic to another destination (VLAN).

- Double Tagging (p46) 

- Double Tagging is another VLAN hopping attack that takes advantage of the 802.1q tagging process. A switch removes the first tag when it processes a frame and sends it through a trunk connection. The next switch in line will process the second tag that points to the destination VLAN. The second switch does not notice the frame’s source, only its tag.
