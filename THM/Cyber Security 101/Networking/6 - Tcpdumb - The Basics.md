

- Tcpdump tool and its libpcap librabry are written in C and C++
- The libpcap library is the foundation for various other networking tools today
- It was ported to MS Windows as wincap

# Basic Packet Capture

## Specify the Network Interface

- The first thing to decide is which network interface to listen to using `-i INTERFACE` 
- You can choose to listem on all available interfaces using `-i any`

## Save the Captured Packets

- You can save a file with `-w FILE`
- The file extension is most commonly set to `.pcap`

## Read Captured Packets from a File

- You can use Tcpdump to read packets from a file by using `-r FILE`

## Limit the Number of Captured Packets

- You can specify the number of packets to capture by specifying the count using `-c COUNT`

## Don't Resolve IP Addresses and Port Numbers

- Tcpdump will resolve IP addresses and print friendly domain names where possible
- Too avoid making suck DNS lookups, you can use the `-n` argument
- You can use the `-nn` to spot both DNS and port number lookups

## Produce Verbose Output

- If you want to print more details about the packets, you can use `-v` 
- The addition of `-v` will print "The time to live, identification, total lenght and options in an IP packet"

## Cheat Sheet

| Command              |     | Explanation                                                       |
| -------------------- | --- | ----------------------------------------------------------------- |
| tcpdump -i INTERFACE |     | Captures packets on a specific network interface                  |
| tcpdump -w FILE      |     | Writes captured packets to a file                                 |
| tcpdump -r FILE      |     | Reads captured packets from a file                                |
| tcpdump -c COUNT     |     | Captures a specific number of packets                             |
| tcpdump -n           |     | Don't resolve IP addresses                                        |
| tcpdump -nn          |     | Don't resolve IP addresses and don't resolve protocol numbers     |
| tcpdump -v           |     | Verbose display; verbosity can be increased with `-vv` and `-vvv` |

# Filtering Expressions

- Considering the number of packets seen by our network card, it is impossible to see everything at once
- We need to be specific and capture what we are interested in inspecting

## Filtering by Host

- You can easily limit the captured packets to this host using `host IP` or `host HOSTNAME`
- Capturing packets requires you to be logged-in as `root` or to use `sudo`
- If you wnat to limit the packets to those from a particular source IP address or hostname, you must use `src host IP` or `src host HOSTNAME`
- You can limit packets to those sent to a specific destination using `dst host IP` or `dst host HOSTNAME`

## Filtering by Port

- To capture all DNS traffic, you can limit the captured packets to those on **port 53**
 **<p style="text-align:center;"> Remember that DNS uses UDP and TCP ports 53 by default  </p>**
- You can limit the packets to those from a particular source port number or to a particular destination port number using `src port PORT_NUMBER` and `dst port PORT_NUMBER`, respectively

## Filtering by Protocol

- You can limit your packet capture to a specific protocol (ip, ip6, udp, tcp and icmp)

## Logical Operators

- Three logical operators that can be handy:

| Operators |     | Description                                                | Examples                     | Captures                        |
| --------- | --- | ---------------------------------------------------------- | ---------------------------- | ------------------------------- |
| AND       |     | Captures packets where both conditions are true            | tcpdump host 1.1.1.1 and tcp | tcp traffic with host 1.1.1.1   |
| OR        |     | Captures packets when either one of the conditions is true | tcpdump udp or icmp          | captures UDP or ICMP traffic    |
| NOT       |     | Captures packets when the condiiton is not true            | tcpdump not tcp              | captures all packets except TCP |

## Cheat Sheet

| Command                                      |     | Explanation                                              |
| -------------------------------------------- | --- | -------------------------------------------------------- |
| `tcpdump host IP` or `tcpdumb host HOSTNAME` |     | Filters packets by IP address or hostname                |
| `tcpdump src host IP`                        |     | Filters packets by specific source host                  |
| `tcpdump dst host IP`                        |     | Filters packets by a specific destination host           |
| `tcpdump por PORT_NUMBER`                    |     | Filters packets by port number                           |
| `tcpdump src port PORT_NUMBER`               |     | Filter packets by the specified source port number       |
| `tcpdump dst port PORT_NUMBER`               |     | Filters packets by the specified destination port number |
| `tcpdump PROTOCOL`                           |     | Filters packets by protocol                              |

# Advanced Filtering

## Header Bytes

- Filter packets based on the contents of a header byte
- Tcpdump allows you to refer to the contents of any byte in the header using the syntax `proto[expr:size]`
	- `proto` refers to the protocol (Example: arp, ether, icmp, ip, ip6, tcp and udp)
	- `expr` indicates the byte offset, where `0` refers to the first byte
	- `size` indicates the number of bytes that interest us: one, two or four (One is by default)


# Displaying Packets

- Tcpdump is a rich program with many options to customize how the packets are printed and displayed


| Output |     | Explanation                                   |     |                                                                                                                |                              |
| ------ | --- | --------------------------------------------- | --- | -------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| `-q`   |     | Quick output: print brief packet information  |     | Shows the timestamp, along with the source and destination IP addresses and source and destination port number | Brief Packet Information     |
| `-e`   |     | Print the link-level header                   |     | Include the MAC addresses, also help you track the source of any unusual packets on your network               | Displaying Link-Level Header |
| `-A`   |     | Show packet data in ASCII                     |     | Display all bytes mapped to English letters, numbers and symbols                                               | Displaying Packets as ASCII  |
| `-xx`  |     | Show packet data in hex                       |     |                                                                                                                |                              |
| `-X`   |     | Show packet headers and data in hex and ASCII |     |                                                                                                                |                              |
