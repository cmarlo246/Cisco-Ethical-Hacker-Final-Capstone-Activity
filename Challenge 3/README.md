Challenge 3: Exploit Open SMB Server Shares - README

Overview
This challenge focuses on identifying and exploiting insecure SMB (Server Message Block) shares that allow anonymous access to sensitive files and directories.
Objective
Use enumeration tools to:

Scan the network for SMB services
Identify shares accessible without authentication
Navigate shared directories to find the flag file
Extract and retrieve the flag code

Target Information

Network Range: 10.5.5.0/24
Target Host: 10.5.5.14
Service: SMB/Samba
Authentication: Anonymous access enabled

Tools Required

Nmap (network scanner)
enum4linux (SMB enumeration tool)
smbclient (SMB client)

Key Steps

Perform network scan to identify hosts running SMB services
Use enum4linux to enumerate available shares
Identify shares accessible without credentials
Connect to shares using smbclient
Navigate directories and subdirectories
Locate and download the flag file
Extract the flag code

Success Criteria

Identified SMB server: 10.5.5.14
Enumerated shares: homes, IPC$, print$, workfiles
Accessible shares: homes, workfiles, print$
Located flag file: sxij42.txt in print$/OTHER
Retrieved flag code: NWs39691

Key Commands
# Network scan
nmap -sV 10.5.5.0/24

# SMB enumeration
enum4linux -S 10.5.5.14

# Connect to shares
smbclient //10.5.5.14/homes
smbclient //10.5.5.14/workfiles
smbclient //10.5.5.14/print$

# Download file
smb: \OTHER\> get sxij42.txt
