Troubleshooting DNS, DHCP, FTP, and EMAIL in Cisco Packet Tracer
📌 Project Overview

This lab focuses on identifying and troubleshooting common issues affecting core enterprise network services:

DHCP (Dynamic Host Configuration Protocol)

DNS (Domain Name System)

FTP (File Transfer Protocol)

Email Server (SMTP / POP3)

The objective is to simulate real-world enterprise network problems and apply systematic troubleshooting techniques using Cisco Packet Tracer.

🏗️ Network Topology

The lab consists of:

1 Router

1 Switch

Multiple PCs (Clients)

1 Server (Running DHCP, DNS, FTP, Email services)

Example Network:

Router (Gateway) – 192.168.10.1
Server – 192.168.10.2
Clients – DHCP Assigned (192.168.10.0/24)

🔍 Troubleshooting Guide
1️⃣ DHCP Troubleshooting
Common Issues:

PC shows APIPA address (169.254.x.x)

Client not receiving IP address

Wrong subnet or default gateway assigned

Steps to Troubleshoot:

✔️ Check DHCP service is ON
Server → Services → DHCP → Ensure service is ON

✔️ Verify DHCP Pool Configuration

Correct Default Gateway

Correct DNS server

Proper Subnet Mask

IP range not exhausted

✔️ Check Router Interface

show ip interface brief


Ensure interface is up/up

✔️ Verify VLAN configuration (if used)
✔️ If different networks → Configure DHCP Relay:

ip helper-address 192.168.10.2


✔️ On Client:
Desktop → IP Configuration → Click DHCP

2️⃣ DNS Troubleshooting
Common Issues:

Cannot access website using domain name

Ping works with IP but not hostname

Steps to Troubleshoot:

✔️ Ensure DNS service is ON
Server → Services → DNS

✔️ Verify DNS Records:
Example:

www.company.com → 192.168.10.2


✔️ Check Client DNS Settings

ipconfig /all


✔️ Test:

ping 192.168.10.2
ping www.company.com


✔️ Clear DNS cache (PC):

ipconfig /flushdns

3️⃣ FTP Troubleshooting
Common Issues:

Cannot connect to FTP server

Authentication failure

Timeout errors

Steps to Troubleshoot:

✔️ Ensure FTP service is ON
Server → Services → FTP

✔️ Verify User Credentials:

Username

Password

✔️ Test from Client:

ftp 192.168.10.2


✔️ Check:

Firewall settings

Correct server IP

Network connectivity:

ping 192.168.10.2

4️⃣ Email Troubleshooting (SMTP / POP3)
Common Issues:

Cannot send or receive emails

Login failure

Server unreachable

Steps to Troubleshoot:

✔️ Enable Email Service
Server → Services → Email

✔️ Configure:

Domain name (example: company.com)

Create users with passwords

✔️ On Client:
Desktop → Email → Configure:

Email address: user@company.com

Incoming mail (POP3): 192.168.10.2

Outgoing mail (SMTP): 192.168.10.2

✔️ Test:
Send email between two users.

✔️ Verify:

DNS resolution

Correct username/password

Network connectivity