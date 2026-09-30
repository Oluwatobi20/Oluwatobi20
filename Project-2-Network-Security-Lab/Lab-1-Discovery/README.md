# Lab 1: Network Discovery & Traffic Analysis
**Project:** Network Security Lab  
**Analyst:** Oluwatobi Oyero  
**Date:** To be completed when the lab is run  
**Environment:** Personal Lab PC - Windows 11 - Home Network - Authorised to test own devices only

## Objective
Understand own host network configuration before securing the network. Use native Windows tools to identify IP, subnet, gateway, DNS, MAC, ARP table and routing table.

## Tools Used
`hostname`, `ipconfig /all`, `arp -a`, `route print`, `nslookup`, `ping`, `tracert`, `netstat`, `nmap`, `Wireshark`

## 1. Host Identification
**Command:** `hostname`  
**Result:**
- Hostname: [to be recorded]
- What it is: Host name assigned to this Windows machine.

**Screenshot:** `evidence/01-hostname.png`

## 2. IP Configuration
**Command:** `ipconfig /all`  
**Result:**
- IPv4 Address: [to be recorded and sanitized]
- Subnet Mask: [to be recorded]
- Default Gateway: [to be recorded]
- DNS Servers: [to be recorded]
- MAC Address (Physical Address): [to be recorded and partially masked before publishing]
- DHCP Enabled: [Yes/No]
- What it means: [to be completed after analysis]

**Screenshot:** `evidence/02-ipconfig-all.png`

## 3. ARP Table - Who have I talked to recently?
**Command:** `arp -a`  
**Result:** List of cached IP-to-MAC mappings.  
**Observation:** [to be completed]

**Screenshot:** `evidence/03-arp-a.png`

## 4. Routing Table - Where does traffic go?
**Command:** `route print`  
**Key lines to identify:**
- `0.0.0.0` -> Default route via gateway
- `127.0.0.0` -> Loopback
- Local subnet route -> directly reachable local network

**Screenshot:** `evidence/04-route-print.png`

## 5. DNS Resolution
**Command:** `nslookup example.com`  
**Result:**
- DNS Server used: [to be recorded]
- Resolved IP address(es): [to be recorded]

**Screenshot:** `evidence/05-nslookup.png`

## 6. Security Observations
- [ ] Review whether SMB/TCP 445 is listening (`netstat -ano`)
- [ ] Review router/gateway administrative security without publishing credentials
- [ ] Investigate unfamiliar ARP entries rather than assuming they are malicious
- [ ] Identify the configured DNS resolver and assess it separately from the discovery results

## 7. Weaknesses & Hardening
| Weakness Found | Risk | Hardening Applied |
|---|---|---|
| [To be determined from evidence] | [TBD] | [TBD] |

## 8. Evidence List
- [ ] `01-hostname.png`
- [ ] `02-ipconfig-all.png`
- [ ] `03-arp-a.png`
- [ ] `04-route-print.png`
- [ ] `05-nslookup.png`
- [ ] `nmap-local.txt`
- [ ] `capture.pcapng`

## Sanitization Done
- [ ] No public IP address
- [ ] No Wi-Fi password or other credentials
- [ ] No VPN credentials/configuration secrets
- [ ] MAC addresses reviewed/partially masked for public evidence
- [ ] Hostname reviewed for personally identifying information
- [ ] Packet capture reviewed before any public upload

> **Safety scope:** Network scanning and packet capture in this lab are limited to systems and networks the analyst owns or is explicitly authorised to test.
