
# Osi Model (Open Systems Interconnection)

- OSI model defines a framework for computer network communications
- The OSI model is composed of seven layers
- The numbering starts with the Physical layer being layer 1, while the top layer, the Application layer, is layer 7


==**<p style="text-align:center;"> "Please Do Not Throw Sausage Pizza Away"</p>==**


![[Pasted image 20260913132233.png]]


| Layers           | Description                                                                                                                     | Example                                   |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- |
| 1 - Physical     | Physical data transmission media                                                                                                | Electrical, optical, and wireless signals |
| 2 - Data Link    | The data link layer describes an agreement between the different systems on the same network segment on how to communicate.<br> | Ethernet (802.3), WiFi (802.11)           |
| 3 - Network      | Logical addressing and routing between networks                                                                                 | IP, ICMP, IPSec                           |
| 4 - Transport    | End-to-end communication and data segmentation                                                                                  | UDP, TCP                                  |
| 5 - Session      | Establishing, maintaining, and synchronising sessions                                                                           | NFS, RPC                                  |
| 6 - Presentation | Data encoding, encryption, and compression                                                                                      | Unicode, MIME, JPEG, PNG, MPEG            |
| 7 - Application  | Providing services and interfaces to applications                                                                               | HTTP, FTP, DNS, POP3, SMTP, IMAP          |

# TCP/IP Model

- One of the strengths of this model is that it allows a network to continue to function as parts of it are out of service
- 5 Layers


| Layer           | Description                                                                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| 5 - Application | The OSI model application, presentation and session layers, i.e., layers 5, 6, and 7, are grouped into the application layer in the TCP/IP model |
| 4 - Transport   | End-to-end communication and data segmentation                                                                                                   |
| 3 - Network     | The OSI model’s network layer is called the Internet layer in the TCP/IP model.                                                                  |
| 2 - Link        | The data link layer describes an agreement between the different systems on the same network segment on how to communicate.                      |
| 1 - Physical    | Physical data transmission media                                                                                                                 |

# IP Addresses and Subnets

- IPv4 e IPv6 (four octets, 32 bits)
- Allows us to represent a decimal number between 0 and 255
- There are 2 types of IP addresses: Public IP addresses and Private IP addresses

## Ranges of private IP

-> 10.0.0.0 - 10.255.255.255 (10/8)
-> 172.16.0.0 - 172.31.255.255 (172.16/12)
-> 192.168.0.0 - 192.168.255.255 (192.168/16)

## Routing 

- A router forwards data packets to the proper network
- Functions at layer 3
- Inspects the IP address and fowards the packet to the router so the packet gets closer to its destination

# UDP and TCP

- Transport protocols

## UDP

- User Data Protocol 
- UDP is a simple connectionless protocol (Layer 4)
- It doesnt requires connection

## TCP

- Trsnsmission Control Protocol
- TCP is a connection-oriented transport protocol (Layer 4)
-  Uses three-way handshake
- Three-way handshake has two flags -> SYN (synchronise) and ACK (acknowledgment)


Three-way handshake:

-> SYN Packet: Sends a SYN packet to the server. This packet contains the client's randomly chosen initial sequence number
-> SYN-ACK Packet: The server responds to te SYN packet with a SYN-ACK packet, wich adds the initial sequence umber randomly chosen by the server
-> ACK Packet: The three-way handshake is completed as the client sends an ACK packet to acknowledge the reception of the SYN-ACK packet

# Encapsulation

- Encapsulation refers to the process of every layer adding a header to the received unit data and sending the encapsulated unit to the layer below
- Is an essencial concept as it allows each layer to focus on its intended function

| Layer                               | Description                                                                                                                                 |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Application data                    | The application formats the data and starts sending it accordingto the application protocol used using the layer below it (Transport Layer) |
| Transport protocol segment/datagram | TCP or UDP adds the proper header information and creates the TCP segment or the UDP datagram. Sebt to the layer below it (Network Layer)   |
| Network packet                      | Adds an IP header to the received TCP or UDP then this ip packet is sent to the layer below (Data lLink Layer)                              |
| Data link frame                     | Adds the proper header and trailer, creating a frame                                                                                        |
