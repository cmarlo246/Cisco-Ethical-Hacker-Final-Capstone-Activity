Challenge 2: Web Server Vulnerabilities - README

Overview
This challenge focuses on identifying and exploiting web server misconfigurations that allow directory listing and unauthorized file access.
Objective
Use reconnaissance tools to:

Identify misconfigured directories on a web server
Enumerate accessible files and subdirectories
Locate and retrieve the flag file

Target Information

Web Server: 10.5.5.12
Application: DVWA
Security Level: Low
Vulnerable Directories: Multiple

Tools Required

Nikto (web vulnerability scanner)
Web browser
Command-line tools

Key Steps

Perform reconnaissance using Nikto to identify vulnerable directories
Identify directories with indexing enabled
Use URL manipulation to browse directory contents
Systematically search subdirectories for flag files
Retrieve and document the flag code

Success Criteria

Identified vulnerable directories: /config/ and /docs/
Located flag file: db_form.html
Found in directory: /config/
Retrieved flag code: aWe-4975

Reconnaissance Command
nikto -h 10.5.5.12
Vulnerable URLs

http://10.5.5.12/config/
http://10.5.5.12/docs/
http://10.5.5.12/config/db_form.html

Security Lessons
This challenge highlights the risks of directory listing vulnerabilities and missing security headers (Content-Type). Proper server configuration, including disabling directory indexing and implementing appropriate HTTP headers, is essential for web server security.
