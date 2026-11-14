
# Host Discovery

- Nmap uses multiple ways to specify its targets
	- IP range using `-`: Scan all the IP addresses from `192.168.0.1` to `192.168.0.10` -> `192.168.0.1-20`
	- IP subnet using `/`: Scan a subnet -> `192.168.0.1/24 = 192.168.0.0-255`
	- Hostname: Specify your target by hostname -> `example.thm`

## Scanning a "Local" Network

- We use the term "local" to refer to the network we are directly connected to
- Because we are scanning the local network, we can look up the `MAC addresses` of the devices
- We can figure out the network card vendors (Enterprise infrastructure, consumer PCS and specialized industrial sectors)
- When scanning a directly connected network, Nmap starts by sending ARP requests. When a device responds to the ARP request, Nmap labels it with "Host is up"

## Scanning a "Remote" Network

- In this context, "remote" means that at least one router separates our system from this network
- Unlike scanning a local network, we cannot send an ARP request to the target
- `nmap -sL` -> This scan only lists the targets to scan without actually scanning them (This option helps confirm the targets before running the actual scan)
- `nmap -sn` -> Aims to discover live hosts without attempting to discover the services running on them

# Port Scanning

- We want to discover the network services listening on those live hosts
- Network service mean any process that is listening for incoming connections on a TCP or UDP port
- Commom network services include web servers, wich usually listen on TCP ports 80 and 443, and DNS servers (UDP and TCP port 53)
- TCP and UDP has 65,535 ports

## Scanning TCP ports

- `telnet`
- With telnet client you need to establish a TCP connection with every target port
- Only open TCP ports would respond and allow TCP connection to be established
- This procedure is not very different from Nmap's connect scan

## Connect Scan

- Can be triggered using `-sT`
- If the TCP port turns out to be open and Nmap connects successfully, Nmap will tear down the established connection

## SYN Scan (Stealth)

- The SYN scan only executes the first step: It sends a TCP SYN packet
- The advantage is that this is expected to lead to fewer logs as the connection is never established
- You can select the SYN scan using the `-sS`

## Scanning UDP Ports

- UDP does not require establishing a connection and tearing it down afterwards
- You can select `-sU` for UDP services

## Limiting the Target Ports

- `-F` for fast mode, scans the 100 most common ports
- `-p[range]` allows you to specify a range of ports to scan

# Version Detection

## OS Detecion

- You can enable OS detection by adding the `-O`  option

##  Service and Version Detection

- You discovered several open ports and want to know what services are listening on them: `-sV` enables version detection

## Forcing the Scan

- When we run our port scan, such as using `-sS`, there is a possibility that the target host does not reply during the host discovery phase
- We can ask Nmap to treat all hosts as online and port scan every host, including those that didnt respond during the host discovery phase
- This choice can be triggered by adding the `-Pn` option

# Timing 

- Running your scan at its normal speed might trigger an IDS (Intrusion Detection System)
- Nmap gives you six timing templates:
	- T0 (paranoid) - 9.8 hours
	- T1 (sneaky) - 27.53 minutes
	- T2 (polite) - 40.52 minutes
	- T3 (normal) - 0.15 seconds
	- T4 (aggressive) - 0.13 seconds
- A second helpful option is the number of parallel service probes. The number of parallel probes can be controlled with `--min-parallelism <numprobes>`
and `--max-parallelism <numbprobes>`
- A similar helpful option is the `--min-rate <number>` and `--max-rate <number>`. They control the minimum and maximum rates at which nmap sends packets
- The last option is `--host-timeout <time>`. This option specifies the maximum time you are willing to wait, and it is suitable for slow hosts or hosts with slow network connections
# Output

## Verbosity and Debugging

- The best way to get more updates about what's happening is to enable verbose output by adding `-v`
- You can increase the verbosity level by adding another "v", such as `-vv` (v2) or even `-vvvv` (v4)
- You can consider the `-d` for debugging-level output
- You can increase the debugging level by adding one more "d" or by specifying the debugging level directly (Maximun level is `-d9`)

## Saving Scan Report

- In many cases, we would need to save the scan results
- The 3 most useful are: 
	- Normal output (human-friendly) -> `-oN <filename>`
	- XML output -> `-oX <filename>`
	- Grepable output (Reference to the grep command) -> `oG <filename>`
	- Output in all major formats -> `-oA <basename>`

# Cheat Sheet


| Option                                                              |     | Explanation                                                                                        |
| ------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------------- |
| `-sL`                                                               |     | List scan - List targets without scanning                                                          |
| -- Host Discovery                                                   |     |                                                                                                    |
| `-sn`                                                               |     | Ping Scan - Host discovery only                                                                    |
| -- Port Scanning                                                    |     |                                                                                                    |
| `-sT`                                                               |     | TCP connect scan - Complete three-way handshake                                                    |
| `-sS`                                                               |     | TCP SYN - Only first step of the three-way handshake                                               |
| `-sU`                                                               |     | UDP Scan                                                                                           |
| `-F`                                                                |     | Fast Mode - Scans the 100 most common ports                                                        |
| `-p[range]`                                                         |     | Specifies a range of port numbers - `-p-` scans all the ports                                      |
| `-Pn`                                                               |     | Treat all hosts as online - Scan hosts that appear to be down                                      |
| -- Service Detection                                                |     |                                                                                                    |
| `-O`                                                                |     | OS detection                                                                                       |
| `-sV`                                                               |     | Service version detection                                                                          |
| `-A`                                                                |     | OS detection, version detection, and other additions                                               |
| -- Timing                                                           |     |                                                                                                    |
| `-T<0-5>`                                                           |     | Timing template - paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5) |
| `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>` |     | Minimum and maximum number of parallel probes                                                      |
| `--min-rate <number>` and `--max-rate <number>`                     |     | Minimum and maximum rate (packets/second)                                                          |
| `--host-timeout`                                                    |     | Maximum amout of time to wait for a target host                                                    |
| -- Real-time output                                                 |     |                                                                                                    |
| `-v`                                                                |     | Verbosity level - For example                                                                      |
| `-d`                                                                |     | Debugging level                                                                                    |
| -- Report                                                           |     |                                                                                                    |
| `-oN <filename>`                                                    |     | Normal output                                                                                      |
| `-oX <filename>`                                                    |     | XML output                                                                                         |
| `-oG <filename>`                                                    |     | grep-able output                                                                                   |
| `-oA <basename>`                                                    |     | Output in all major formats                                                                        |
