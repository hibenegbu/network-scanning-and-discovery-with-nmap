# network-scanning-and-discovery-with-nmap

This repository contains the Network Scanning and Discovery with Nmap project, where I demonstrated network reconnaissance, host discovery, port scanning, and service enumeration techniques using Nmap in a virtual environment. The project includes detailed instructions, scan commands, and screenshots of my process, providing insight into practical network scanning.
Table of Contents
- **Introduction
•	Tools Used
•	Environment Setup
•	Project Overview
o	1. Basic Scan
o	2. Network Range Scan
o	3. SYN Scan (Stealth Scan)
o	4. Service and Version Detection
o	5. Conclusion
- **Introduction
In this project, I performed network scanning and discovery using Nmap on a virtual network environment set up in VirtualBox. The goal was to identify the network's open ports, services, and active devices. The project focuses on practical network reconnaissance techniques used in vulnerability discovery.
Tools Used
- **Nmap: Tool for network scanning and service enumeration.
•	VirtualBox: Virtual environment for network testing.
•	Kali Linux: Used as the scanning machine.
- **Environment Setup
I set up a virtual environment using VirtualBox with Kali Linux as the primary scanning machine. The Kali Linux machine was configured in NAT mode, with the IP address 10.0.2.15 assigned.
Project Overview
1. Basic Scan
I performed a basic scan on the local machine (IP: 10.0.2.15) to identify open ports and services.
Command:
bash
Copy code
nmap 10.0.2.15
Output:
kotlin
Copy code
Starting Nmap 7.94 ( https://nmap.org ) at 2024-10-02
Nmap scan report for 10.0.2.15
The host is up (0.00056s latency).
Not shown: 999 closed ports
PORT     STATE  SERVICE
22/tcp   open   ssh
Analysis: The scan identified that port 22 (SSH) was open, indicating the SSH service was running.
2. Network Range Scan
Next, I scanned the entire virtual network range 10.0.2.1-254 to detect other active devices and services within the network.
Command:
bash
Copy code
Nmap 10.0.2.1-254
Output:
kotlin
Copy code
Nmap scan report for 10.0.2.1 (Host is up)
Nmap scan report for 10.0.2.3 (Host is up)
Nmap scan report for 10.0.2.15 (Host is up)
PORT     STATE  SERVICE
22/tcp   open   ssh
Analysis: Multiple devices were identified in the virtual network, including the local machine, but no additional services were detected on other devices.
3. SYN Scan (Stealth Scan)
I conducted a SYN (stealth) scan to identify open ports more stealthily.
Command:
bash
Copy code
nmap -sS 10.0.2.15
Output:
kotlin
Copy code
Nmap scan report for 10.0.2.15
The host is up (0.00047s latency).
PORT     STATE  SERVICE
22/tcp   open   ssh
Analysis: The SYN scan confirmed that port 22 (SSH) was the only open port, similar to the basic scan results.
4. Service and Version Detection
I performed a service and version detection scan to obtain detailed information on running services.
Command:
bash
Copy code
nmap -sV 10.0.2.15
Output:
swift
Copy code
PORT     STATE  SERVICE      VERSION
22/tcp   open   ssh          OpenSSH 8.2p1 Debian 4 (protocol 2.0)
Analysis: The scan revealed that the SSH service on port 22 was running OpenSSH 8.2p1, which is important for identifying potential vulnerabilities.
5. Conclusion
This project allowed me to explore different Nmap scanning techniques and better understand network reconnaissance. From basic scans to SYN scans and service/version detection, I successfully identified the running services in a virtual environment, an essential skill in network security and vulnerability discovery.

![image](https://github.com/user-attachments/assets/76b6aae3-55a4-48c4-aa52-246b8b63307f)
