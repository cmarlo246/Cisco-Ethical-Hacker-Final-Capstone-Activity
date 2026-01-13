Challenge 4: Analyze a PCAP File to Find Information - README

Overview
This challenge focuses on network forensics and packet analysis to identify security vulnerabilities and extract sensitive information from captured network traffic.
Objective
Use Wireshark to:

Analyze captured network traffic (PCAP file)
Identify the target IP address
Discover accessible directories and files
Locate and retrieve the flag file via web browser
Extract the flag code

Target Information

PCAP File Location: /home/kali/Downloads/SA.pcap or /home/kali/OTHER/SA.pcap
Target IP Addresses: 10.5.5.11 or 10.5.5.14
Protocol: HTTP (unencrypted)

Tools Required

Wireshark (packet analyzer)
Web browser
Command-line tools

Key Steps

Open and analyze the SA.pcap file in Wireshark
Filter HTTP traffic to identify target IP addresses
Examine HTTP requests to discover accessible directories
Document all revealed directories and URLs
Use web browser to access discovered directories
Locate the flag file
Extract and document the flag code

Success Criteria

Identified target IPs: 10.5.5.11 or 10.5.5.14
Discovered directories:

/database-offline.php
/styles/global-styles.css
/test
/data
/webservices/rest/ws-user-account.php
/includes
/passwords
/icons.text/gif
/webservices/soap/lib


Located flag file: 10.5.5.14/data/accounts.xml
File contains: User credentials and passwords
Retrieved flag code: zz90014x

Analysis Tips

Use Wireshark display filters: http or http.request
Follow HTTP streams to see complete conversations
Look for GET/POST requests revealing directory structures
Pay attention to response codes (200 OK indicates accessible resources)

Security Lessons
This challenge demonstrates the critical importance of encrypting data in transit. Transmitting sensitive information over unencrypted HTTP allows attackers to intercept credentials, file contents, and other confidential data. Organizations must implement HTTPS/TLS encryption and proper access controls to protect data confidentiality.
