
- Wireshark is an open-source network packet analyser tool capable of sniffing and investigating live traffic and inspecting packet captures (PCAP)

# Packet Dissection 

- Also know as protocol dissection, wich investigates packet details by decoding available protocols and fields

## Packet Details

- Packets consist of 5 to 7 layers based on the OSI Model

Seven distinct layers to the packet:
- Frame/packet
- Source [MAC]
- Source [IP]
- Protocol
- Protocol errors
- Application protocol
- Application data

![[Pasted image 20260930200835.png]]

-> The Frame (Layer 1): This will show what frame/packet you are looking at and details specific to the Physical layer of the OSI Model

![[Pasted image 20260930201158.png]]

-> Source [MAC] (Layer 2): This will show you the sourcce and destination MAC Addresses; from the Data Link layer of the OSI Model 

![[Pasted image 20260930201306.png]]

-> Source [IP] (Layer 3): This will show you the source and destination IPv4 Addresses; from the Network layer of the OSI Model

![[Pasted image 20260930201406.png]]

-> Protocol (Layer 4): This will show you details of the protocol used (UDP/TCP) and source and destination ports; from the Transport layer of the OSI Model

![[Pasted image 20260930201518.png]]

-> Protocol Erros: This continuation of the 4th layer shows specfic segments from TCP that needed to be reassembled

![[Pasted image 20260930201631.png]]

-> Application Protocol (Layer 5): This will show details specific to the protocol used, such HTTP, FTP and SMB. From the Application layer of the OSI Model

![[Pasted image 20260930201800.png]]

-> Application Data: This extension of the 5th layer can show application-specific data

![[Pasted image 20260930201847.png]]

# Packet Navigation

# Packet Filtering
