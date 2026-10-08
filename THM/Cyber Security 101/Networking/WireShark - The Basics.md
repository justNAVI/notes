 
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

-> **The Frame (Layer 1):** This will show what frame/packet you are looking at and details specific to the Physical layer of the OSI Model

![[Pasted image 20260930201158.png]]

-> **Source [MAC] (Layer 2):** This will show you the sourcce and destination MAC Addresses; from the Data Link layer of the OSI Model 

![[Pasted image 20260930201306.png]]

-> **Source [IP] (Layer 3):** This will show you the source and destination IPv4 Addresses; from the Network layer of the OSI Model

![[Pasted image 20260930201406.png]]

-> **Protocol (Layer 4):** This will show you details of the protocol used (UDP/TCP) and source and destination ports; from the Transport layer of the OSI Model

![[Pasted image 20260930201518.png]]

-> **Protocol Erros:** This continuation of the 4th layer shows specfic segments from TCP that needed to be reassembled

![[Pasted image 20260930201631.png]]

-> **Application Protocol (Layer 5):** This will show details specific to the protocol used, such HTTP, FTP and SMB. From the Application layer of the OSI Model

![[Pasted image 20260930201800.png]]

-> **Application Data:** This extension of the 5th layer can show application-specific data

![[Pasted image 20260930201847.png]]

# Packet Navigation

## Go to Packet

- This feature not only navigates between packets up and down
- Provides in-frame packet tracking and finds the next packet in the particular part of conversation
- Use `"Go"` menu and toolbar to view specfic packets

## Find Packets

- Wireshark can find packets by packet content
- `"Edit --> Find Packet"` menu to make a search inside the packets for a particular event
- This funcionality acceprts 4 types of input (Display filter, Hex, String and Regex)

## Mark Packets

- Helpful functionality for analysts
- You can find/point to a specific packet for further investigation by marking it
- `"Edit"` or the `"right-click"` menu to mark/unmark packets

## Packet Commets

- Commenting is another helpful feature for analysts
- `Right-click -> Packets Comments -> Add New Comments`
- Unlike packet marking, the comments can stay within the capture file until operator removes them
## Export Packets

- This funcionality helps analysts share the only suspicious packets (decided scope)
- You can use the `"File"` menu to export packets

## Export Objects (Files)

- Export objects are availabe only for selected protocol's streams (DICON, HTTP, IMF, SMB and TFTP)

## Time Display Format

- By default Wireshark shows time in "Seconds Since Beginning of Capture"
- Foa a better view:  `View --> Time Display Format` ---> UTC Data and Time of Day

## Expert View

- Wireshark also detects specific states of protocols to help analysts easly spot possible anomalies and problems
- You can use the "lower left bottom section" in the status bar or `Analyse --> Expert Information` menu to view all available information entries via a dialogue box

![[Pasted image 20261004125846.png|700]]

# Packet Filtering

- Wireshark has two types of filtering spproaches: Capture and Display filters
- **Capture filters**: Used fot "capturing" only the packets valid for the used filter
- **Display filters**: Used for "viewing" the packets valid for the used filter 
- Filters are specific queries designed to protocols available in Wireshark


- There are two different ways to filter traffic and remove noise from capture file:

1. Uses queries
2. Uses the righet-click menu

**GOLDEN RULE:**
 <div align="center"> "If you can click on it, you can filter and copy it"</div>

## Apply Filter 

- While investigating a capture file, you can click on the field you want to filter and use the "right-click menu" or "Analyse --> Apply as FIlter" menu to filter the specific value
- The number of total and displayed packets are always shown on the status bar
-  When you use the "Apply as a Filter" option you will filter only a single entity of the packet
- Good way of investigating a particular value in packets

## Conversation Filter

-  Conversation filter option helps you view only related packets and hide the rest of the packets easily
- `Right-click menu` or `Analyse --> Conversation Filter` menu to filter conversations 

## Colourise Conversation

- Similar to Conversation Filter
- The difference: It highlightts the linked packets without applying a display filter and decresing the number of viewed packets
- `Right-clik menu` or `view --> Colourise Conversation` menu to colourise a linked packet in a single click
- You can use `View --> Colourise Conversation --> Reset Colourisation` to redo it 

## Prepare as Filter

- Similar to "Apply as Filter", this option helps analysts create displays filters using "right-click" menu
- It adds the require query to the pane and waits for execution command (enter) or another chosen filtering option by using "`...and/or...`" fromm the "right-click menu"

## Apply as Column

- By default, the packet list pane provides basic information about each packet
- "Right-click menu" or `Analyse --> Apply as Column` menu to add columns to the pakcet list pane 
- Onde you click on value and apply it as column, it will be visible on the packet list pane
- This function helps analyts examime teh apparence of a specific value/filed cross the available packets in the capture file

## Follow Stream

- Wireshark displays everything in packet portion size
- It is possible to reconstruct the streams and view the raw traffic as it is presented at the application leve
- It is also possible to view the unencrypted protocol data like usernames, passwords and other transferred data
- "Right-click menu" or `Analyse --> Follow TCP/UDP/HTTP Stream` menu to follow traffic streams 
- Packets orginating from the server are highligted with **BLUE**
- Packets originating from client re highlighted wih **RED**
- Once a filter is applied, the number of viewed packets will change

## Simple Display Filter Queries

- The easiest wat to filter quickly the huge amount of packets is by applying a display filter using the "Apply a display filter" bar show on top

### Filter by Protocol Name or Port 

#### Protocol Name

- Protocol Name: simply type in the protocol name and hit enter
- **Keywords:** `arp`, `dhcp`, `smtp`, `pop`, `imap`, and more 

#### Port Number

- You can use the structure:

```
tcp.port == <port number>
udp.port == <port number>
```

- Example -> If you want to see only http packets

`tcp.port == 80`

#### IP
- Is often a need to filter for a specific IP
- To filter for a specific IP, you can use the structure:

```
ip.addr == <IP address>
```

- Example -> If you need to search for the PI 192.168.1.2

`ip.addr == 192.168.1.2`


