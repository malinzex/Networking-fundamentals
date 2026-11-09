# INTRODUCTION TO NETWORKING

## What Is a Computer Network?

A computer network is a group of interconnected devices that communicate and exchange information with one another.

These devices may include:

- Computers.
- Smartphones.
- Servers.
- Printers.
- Routers.
- Switches.
- Smart devices.

Networks allow devices to share resources, exchange data, and access services such as the internet.

![Network Topology](Network%20Topology.png)

## Understanding IP Addresses

An Internet Protocol (IP) address is a numerical address assigned to a network interface to identify it and enable communication over an IP network.

IP addresses help devices send and receive data across networks.

There are two major versions:

- IPv4: Uses a 32-bit addressing system.
- IPv6: Uses a 128-bit addressing system.

### Private IP Address

A private IP address is used within a private network, such as a home or office network.

Devices connected to a home router commonly receive private IP addresses.

Examples of private IPv4 address ranges include:

| Range | Address block |
|---|---|
| Class A private range | 10.0.0.0 – 10.255.255.255 |
| Class B private range | 172.16.0.0 – 172.31.255.255 |
| Class C private range | 192.168.0.0 – 192.168.255.255 |

Private IP addresses are not directly routable across the public internet.

### Public IP Address

A public IP address is an address used to identify a network or device on the public internet.

Internet Service Providers (ISPs) typically assign public IP addresses to customer internet connections.

A router commonly uses its public IP address for communication with external networks, often through Network Address Translation (NAT).

### Private IP vs Public IP

| Private IP | Public IP |
|---|---|
| Used within private networks | Used on the public internet |
| Not directly routable over the public internet | Globally routable, subject to network configuration |
| Commonly assigned by a local router or DHCP server | Commonly assigned by an ISP |
| Example: 192.168.1.10 | Example: An ISP-assigned public IPv4 address |

## Understanding MAC Addresses

A Media Access Control (MAC) address is a link-layer identifier associated with a network interface.

It is commonly represented as six pairs of hexadecimal characters.

Example:

`00:1A:2B:3C:4D:5E`

MAC addresses are used for communication within a local network at the data link layer.

**Important:** Although hardware manufacturers commonly assign MAC addresses to network interfaces, MAC addresses can be changed or randomized through software.

### IP Address vs MAC Address

| IP Address | MAC Address |
|---|---|
| Used for network-layer addressing | Used for link-layer addressing |
| Can change depending on network configuration | Commonly assigned to a network interface |
| Used for routing between networks | Used for local network frame delivery |
| IPv4 and IPv6 formats | Commonly represented in hexadecimal |

## Dynamic Host Configuration Protocol (DHCP)

DHCP stands for Dynamic Host Configuration Protocol.

It is a network protocol that automatically provides devices with IP configuration information when they connect to a network.

A DHCP server can assign:

- IP addresses.
- Subnet masks.
- Default gateways.
- DNS server addresses.
- Lease durations.

For example, when a laptop connects to a Wi-Fi network, the router's DHCP service may automatically assign it an IP address.

### DHCP Four-Step Process

DHCP commonly follows a four-step process known as DORA:

1. **Discover:** The client broadcasts a DHCP Discover message to find available DHCP servers.
2. **Offer:** A DHCP server responds with an available IP address and configuration information.
3. **Request:** The client requests the offered IP address.
4. **Acknowledge:** The DHCP server confirms the lease and completes the assignment.

DHCP commonly uses UDP ports 67 and 68.

![DHCP DORA Process](DHCP%20Dora%20Process.png)

# NETWORK COMMUNICATION PROTOCOLS

## Transmission Control Protocol (TCP)

TCP stands for Transmission Control Protocol.

It is a connection-oriented transport-layer protocol that provides reliable data transmission between devices over an IP network.

TCP provides:

- Reliable data delivery.
- Error detection.
- Retransmission of lost data.
- Ordered delivery of data.
- Flow control.
- Congestion control.

TCP is commonly used by applications that require reliable communication.

Examples include web browsing, email, and file transfers.

### TCP Three-Way Handshake

Before establishing a TCP connection, the client and server perform a process called the TCP Three-Way Handshake.

The process consists of three steps:

**Step 1: SYN (Synchronize)**

The client sends a SYN packet to the server to request a connection and initiate sequence number synchronization.

**Step 2: SYN-ACK (Synchronize-Acknowledge)**

The server responds with a SYN-ACK packet, acknowledging the client's request and sending its own synchronization information.

**Step 3: ACK (Acknowledge)**

The client sends an ACK packet to acknowledge the server's response.

The TCP connection is now established, and data transmission can begin.

### Summary

| Step | Packet | Action |
|---|---|---|
| 1 | SYN | Client requests a connection |
| 2 | SYN-ACK | Server acknowledges and responds |
| 3 | ACK | Client acknowledges the response |

![TCP Three-Way Handshake](TCP%20Three%20Way%20Handshake.png)

## User Datagram Protocol (UDP)

UDP stands for User Datagram Protocol.

It is a connectionless transport-layer protocol that allows devices to send data without establishing a connection before transmission.

Unlike TCP, UDP does not guarantee delivery, ordering, or retransmission of lost packets.

However, it has lower protocol overhead and can be useful for applications where speed and low latency are important.

### Common Uses of UDP

1. Online gaming.
2. Live audio and video streaming.
3. Video conferencing.
4. DNS queries.
5. Real-time communication.

### TCP vs UDP

| TCP | UDP |
|---|---|
| Connection-oriented | Connectionless |
| Reliable delivery | No delivery guarantee |
| Uses acknowledgements and retransmissions | Does not provide built-in retransmission |
| Maintains ordered delivery | Does not guarantee packet order |
| Generally higher protocol overhead | Generally lower protocol overhead |
| Suitable for reliable data transfer | Suitable for many real-time applications |

## Hypertext Transfer Protocol (HTTP)

HTTP stands for Hypertext Transfer Protocol.

It is an application-layer protocol used for communication between web clients and web servers.

HTTP allows clients, such as web browsers, to request resources from servers.

Examples include:

- Web pages.
- Images.
- Documents.
- Other web resources.

HTTP commonly uses TCP port 80.

## Hypertext Transfer Protocol Secure (HTTPS)

HTTPS stands for Hypertext Transfer Protocol Secure.

It is the secure version of HTTP, using TLS (Transport Layer Security) to protect communication between a client and a server.

HTTPS provides:

- Encryption of data in transit.
- Authentication of the server through digital certificates.
- Protection against undetected modification of transmitted data.

HTTPS commonly uses TCP port 443.

### HTTP vs HTTPS

| HTTP | HTTPS |
|---|---|
| Does not provide TLS encryption | Uses TLS encryption |
| Commonly uses TCP port 80 | Commonly uses TCP port 443 |
| Data is not protected by TLS | Data is protected in transit by TLS |
| Less suitable for sensitive communication | Recommended for secure web communication |

# COMMON NETWORK PORTS

## Understanding Network Ports

A port is a logical communication endpoint used by transport-layer protocols such as TCP and UDP.

Ports help a computer direct incoming and outgoing network traffic to the appropriate application or service.

For example, when you visit a website, your browser communicates with a web server using a specific port.

### Commonly Used Network Ports

| Port Number | Service | Description |
|---|---|---|
| 20 | FTP | FTP data transfer in active mode |
| 21 | FTP | FTP control connection |
| 22 | SSH | Secure remote access |
| 23 | Telnet | Remote terminal communication |
| 25 | SMTP | Email transmission |
| 53 | DNS | Domain name resolution |
| 67 | DHCP | DHCP server |
| 68 | DHCP | DHCP client |
| 80 | HTTP | Unencrypted web communication |
| 110 | POP3 | Email retrieval |
| 123 | NTP | Network time synchronization |
| 443 | HTTPS | Secure web communication |
| 8080 | HTTP alternate | Commonly used as an alternative HTTP port |

**Important networking notes:**

- Port 53 can use both UDP and TCP.
- DHCP commonly uses UDP ports 67 and 68.
- DNS commonly uses UDP, but TCP is also used in specific situations.
- Port 8080 is commonly used for alternative HTTP services, proxies, and development servers.
- Telnet does not encrypt its communication and is generally discouraged for secure remote administration.
- Port numbers identify services, but their presence alone does not prove that a service is running or that a system is vulnerable.



## Understanding network ports is important for:

- Network troubleshooting.
- Firewall configuration.
- Identifying running services.
- Investigating suspicious network activity.
- Understanding network exposure.
- Security monitoring and incident response.

Cybersecurity analysts often examine network ports to understand which services are communicating and whether unexpected services or connections require investigation.


## Conclusion

Cybersecurity begins with understanding how systems work, identifying where weaknesses exist, and recognizing how those weaknesses could be exploited.
