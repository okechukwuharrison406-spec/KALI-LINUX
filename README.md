# KALI-LINUX
# 🐉 Lab 4: Kali Linux — Setup & Configuration
**Installation → Post-Config → Tools Verification → Lab Integration → Attack Readiness**

---

## Overview
Installed and fully configured Kali Linux as a dedicated penetration testing machine
inside a virtual environment — covering OS installation, post-configuration, tool
verification, lab network integration, and preparation for active security testing
including Active Directory attacks, vulnerability scanning, and credential testing.

## Lab Steps Covered
| Step | Task |
|------|------|
| 01 | Create and configure Kali Linux virtual machine |
| 02 | Boot from ISO — select Graphical Install |
| 03 | Language, location, keyboard configuration |
| 04 | Network / hostname configuration during install |
| 05 | Create user account (non-root by default) |
| 06 | Partition disk — guided single partition |
| 07 | Select software — kali-linux-default metapackage |
| 08 | Install GRUB bootloader — complete installation |
| 09 | Post-install: full system update, guest additions, timezone, hostname |
| 10 | Network configuration for lab environment (static IP, DNS) |
| 11 | Enable and configure SSH server |
| 12 | Verify pre-installed tools (Nmap, Metasploit, Hydra, Wireshark, etc.) |
| 13 | Install additional tools: Impacket, CME, ShellGPT, GVM/OpenVAS |
| 14 | Configure for AD attacks: BloodHound, Responder, Evil-WinRM |
| 15 | Take baseline snapshot for lab rollback |

## Tools Installed and Configured
```
Reconnaissance  : Nmap, Netdiscover, Enum4linux
AD Attacks      : Impacket, BloodHound, CrackMapExec, Responder, Evil-WinRM
Credentials     : Hydra, John the Ripper, Hashcat
Exploitation    : Metasploit Framework
Web Security    : Burp Suite, SQLmap, Nikto, Gobuster
Vulnerability   : GVM / OpenVAS
AI Terminal     : ShellGPT
Network         : Wireshark, Tcpdump, Netcat
```

## Key Commands
```bash
# Full system update
sudo apt update && sudo apt full-upgrade -y

# Network host discovery
nmap -sn 192.168.x.0/24

# AS-REP Roasting (no credentials needed)
GetNPUsers.py DOMAIN/ -no-pass -dc-ip <DC-IP> -request

# Brute-force SQL Server port 1433
hydra -l sa -P /usr/share/wordlists/rockyou.txt <target> mssql

# Crack AS-REP hash offline
hashcat -m 18200 hash.txt /usr/share/wordlists/rockyou.txt

# Start BloodHound data collection
bloodhound-python -d DOMAIN -u user -p pass -dc <DC-IP> -c all

# LLMNR poisoning (lab use only)
sudo responder -I eth0 -rdwv

# WinRM remote shell
evil-winrm -i <target> -u user -p pass
```

## Security Concepts Demonstrated
- LLMNR/NBT-NS poisoning via Responder (passive credential capture)
- AS-REP Roasting — attacking accounts with Kerberos pre-auth disabled
- Kerberoasting — offline cracking of service ticket hashes
- BloodHound attack path mapping across Active Directory
- SQL Server brute-force via Hydra on port 1433
- NTLM hash cracking with Hashcat (GPU-accelerated)
- VM snapshot discipline for professional lab management

## Tools
`Kali Linux` `Nmap` `Metasploit` `Hydra` `Impacket` `BloodHound`
`Responder` `CrackMapExec` `Hashcat` `John` `Evil-WinRM` `ShellGPT` `GVM`

## Skills
`Linux Administration` `Penetration Testing` `Active Directory Attacks`
`Network Scanning` `Credential Attacks` `Vulnerability Scanning` `SSH`
*[LinkedIn](https://linkedin.com/in/Harrison-Okechukwu) |
[GitHub](https://github.com/HarrisonOkechukwu)*
