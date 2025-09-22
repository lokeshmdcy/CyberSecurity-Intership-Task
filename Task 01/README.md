# Task 1 — Local Network Port Scan

## Project Overview
Scan the local network to discover open ports and services, analyze security exposure, and provide remediation recommendations.

## Tools
- Nmap (https://nmap.org)
- Terminal / PowerShell

## Environment
- OS: Windows 11 /Ubuntu 22.04
- Nmap version: 7.98
- Scanned range: `192.168.1.0/24`
- Scan date: `Mon Sep 22 2025`

## Key Findings
- Host found: `192.168.1.1`  
- List of open ports found while scanning the host:  
  *(Include full `scan_results.txt` in the repo.)*

## Short Risk Summary
- **SMB/RPC (135/139/445):** High risk — can be used for lateral movement and ransomware.  
- **DB ports (1521/3306):** High risk — sensitive data exposure if accessible.  
- **Management ports (902/912) & web (8080):** Medium — may expose admin interfaces.

## Recommended Actions
- Block or restrict inbound access to the listed ports using a firewall.  
- Stop or disable unnecessary services.  
- Restrict DB ports to `localhost` or an admin subnet.  
- Apply latest patches and enforce strong authentication.
- Re-run nmap -sV for version detection and follow up with vulnerability scans.

## Repo contents
- Task 1 PortScan.docx
- scan_results.txt (raw Nmap output)
- Screenshot of the Scan using Nmap
- REPORT.md (detailed report)

## Commands used
```bash
# Basic TCP SYN scan and save output
nmap -sS -oN scan_results.txt 192.168.56.0/24
