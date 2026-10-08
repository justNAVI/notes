
# TLS

- Transport Layer Security
- Cryptographic protocol operating at the transport layer (OSI Model)
- Confidentiality and Integrity, TSL ensures that no one can read or modify the exchanged data

# HTTP

- Uses port 80 by default

## HTTP over TLS

Requesting a page over HTTPS will require the following 3 steps

1. Estabilish a TCP three-way handshake with the target server
2. Estabilish a TLS session
3. Communicate using the HTTP protocol

- The exchanged traffic is encrypted. There is no way to know the contents without acquiring the encryption key

## Getting the Encryption Key

- The main difference starts with the HTTP protocol (Marked as 3), we can see when the client issues a GET 

![[Pasted image 20260929150642.png]]

# SMTPS, POP3S and IMAPS

Insecure version:

| Protocol | Default Port Number |
| -------- | ------------------- |
| HTTP     | 80                  |
| SMTP     | 25                  |
| POP3     | 110                 |
| IMAP     | 143                 |

Secure Version:

| Protocol | Default Port Number |
| -------- | ------------------- |
| HTTP     | 443                 |
| SMTP     | 465 and 587         |
| POP3     | 995                 |
| IMAP     | 993                 |

# SSH

- Secure Shell
- OpenSSH (open-source implementation of SSH)
- Listens on port 22

OpenSSH several benefits:

-> Secure authentication: Suports public key and two-factor authentication
-> Confidentiality: End-to-end encryption.
-> Integrity: Cryptography protrctys the integrity of the traffic
-> Tunneling: Can create a secure "tunel" to route other protocols through SSH. Leads to a VPN-like connection
-> X11 Fowarding: If you connect to a Unix-like system with a UI, SSH allow you to use the graphical application. The argument -X is required to support it (Example: ssh 192.168.124.148 -X)

# SFTP and FTPS

- SFTP stands for SSH FIle Transfer Porotocol
- FTPS = File Transfer Protocol Secure (Uses TLS)
- Listens on port 22
- Connect using: sftp navi@hostname
- SFTP commands are like Unix-like and differ from FTP commands

| Protocol | Port Number | Commands                                            | Full Name                     |                                |
| -------- | ----------- | --------------------------------------------------- | ----------------------------- | ------------------------------ |
| SFTP     | 22          | sftp username@hostname / get filename / putfilename | SSH FIle Transfer Protocol    | Part of the SSH protocol suite |
| FTPS     | 990         | Unix-like                                           | File Transfer Protocol Secure | Uses TLS                       |
# VPN


- Virtual Private Network
- VPN is very convenient and inexpensive 
- Requirementrs are Internet connectivity and a VPN server and client
- Once a VPN tunnel is established, all our Internet traffic will be routed over the VPN tunnel
- They will not see our public IP address but the VPN server's
- The VPN server may be configured to give you access to private network
