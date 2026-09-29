
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

# HTTP(S)

- This protocol relies on TCP and defines how your web browser communicates with the web servers
- HTTP and HTTPS commonly use TCP port 80 and 443

| Methods | Description                                                                                     |
| ------- | ----------------------------------------------------------------------------------------------- |
| GET     | Retrives data from a server                                                                     |
| POST    | Allow us to submit new data to the server                                                       |
| PUT     | Is used to create a new resourcw on the server and to update and overwrite existing information |
| DELETE  | IS used to delete a specified file or resource on the server                                    |
