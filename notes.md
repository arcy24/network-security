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


