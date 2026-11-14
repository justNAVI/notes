
# DNS (Domain Name System)

- DNS operates at the Application Layer (Layer 7)
- DNS traffic uses UDP (port 53) by default and TCP (port 53) as default fallback


| Record       | Description                                                                                         | Example                        |
| ------------ | --------------------------------------------------------------------------------------------------- | ------------------------------ |
| A Record     | The A (Address) record maps a hostname to IPv4 addresses                                            | example.com -> 172.17.2.172    |
| AAAA Record  | Similar to the A Record, but it is for IPv6                                                         |                                |
| CNAME Record | The CNAME (Canonical Name) record maps a domain name to another domain name                         | www.example.com -> example.com |
| MX Record    | TE MX (Mail Exchange) record sficifies the mail server responsible for handling emails for a domain |                                |

# WHOIS

# HTTP(S): Accessing the Web

- This protocol relies on TCP and defines how your web browser communicates with the web servers
- HTTP and HTTPS commonly use TCP port 80 and 443

| Methods | Description                                                                                     |
| ------- | ----------------------------------------------------------------------------------------------- |
| GET     | Retrives data from a server                                                                     |
| POST    | Allow us to submit new data to the server                                                       |
| PUT     | Is used to create a new resourcw on the server and to update and overwrite existing information |
| DELETE  | Is used to delete a specified file or resource on the server                                    |

# FTP: Transferring Files

- File Transfer Protocol is designed
- Listens on TCO port 21 by default 


| Commands       | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| USER           | Is used to input the username                                |
| PASS           | Is used to enter the password                                |
| RETR (retrive) | Is used to download a file from the FTP server to the client |
| STOR (store)   | Is used to upsload a file from the client to the FTP server  |

# SMTP: Sending Email

- Simple Mail Transfer Protocol defines how a mail client talks with a mail server and how a mail server talks to another 
- The SMTP server listens on TCP port 25 by default

| Commands     | Description                                                                   |
| ------------ | ----------------------------------------------------------------------------- |
| HELO or EHLO | Initiates an SMTP session                                                     |
| MAIL FROM    | Specifies the sender's email address                                          |
| RCPT TO      | Specifies rhe recipient's email address                                       |
| DATA         | Indicates that the client will befing sending the content of the mail message |
| .            | Is sent on a line by itself to indicate the end of the email message          |

# POP 3: Receiving Email

- Post Office Protocol verson 3 is designed to allow the client to communicate with a mail server and retrieve email messages
- An email client sends its messages by relying on SMTP and retrieves then using POP3
- Listens on TCP port 110 by default


(Without the ' .)

| Commands               | Description                                    |
| ---------------------- | ---------------------------------------------- |
| USER <'username>       | Identifies the user                            |
| PASS <'password>       | Provides the user's password                   |
| STAT                   | Requests the number of messages and total size |
| LIST                   | Lists all messages and their sizes             |
| RETR <'message_number> | Retrieves the specified message                |
| DELE <'message_number> | Marks a message for deletion                   |
| QUIT                   | Ends the POP3                                  |

# IMAP: Synchronizing Email

- Internet Message Accress Protocol allow synchronizing read, moved and deleted messages.
- Listen n TCP port 143 by default

(Without the ' .)


| Commads                                | Description                                                       |
| -------------------------------------- | ----------------------------------------------------------------- |
| LOGIN <'username> <'password>          | Authenticates the user                                            |
| SELECT <'mailbox>                      | Selects the mailbox folder to work with                           |
| FETCH <'mail_number> <'data_item_name> | Example FETCH 3 body[] to fetch message number 3, header and body |
| MOVE <'sequence_set> <'mailbox>        | Moves the specified messages to another mailbox                   |
| COPY <'sequence_set> <'data_item_name> | Copies the specified messages to another mailbox                  |
| LOGOUT                                 | Logs out                                                          |

# Conclusion

-> CHEAT SHEET:

![[Pasted image 20260929142948.png]]