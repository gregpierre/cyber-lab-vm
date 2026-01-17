# Cybersecurity Lab VM

A virtual cybersecurity lab environment built on **Kali Linux 2025.3 (VMware Workstation)** — designed for hands-on exploration of **offensive, defensive, and analytical security tools**.

> 💡 *Part of my personal cybersecurity learning environment. This project provides a ready-to-use Kali Linux lab preconfigured for both offensive and defensive tool exploration.*

---

## ⚙️ Overview

This virtual machine serves as a controlled lab setup for cybersecurity learning and experimentation.  
It provides an isolated environment to safely test exploits, analyze network traffic, and evaluate threat detection tools.

**Platform:** VMware Workstation (Windows)  
**Operating System:** Kali Linux 2025.3  
**VM Name:** Cybersecurity Lab  
**Specs:** 4 GB RAM, 4 Processors, 30 GB Disk  
**Network Adapter:** NAT  

---

## Installed Tools

The lab includes a curated selection of tools installed via [`install_kali_tools.sh`](scripts/install_kali_tools.sh).

### Offensive Security Tools
| Category | Tools |
|-----------|--------|
| Reconnaissance | `nmap`, `masscan`, `gobuster`, `whois` |
| Web Exploitation | `sqlmap`, `nikto`, `wpscan` |
| Frameworks | `metasploit-framework`, `burpsuite` |
| Password Attacks | `hydra`, `john`, `hashcat` |

### Defensive / Analysis Tools
| Category | Tools |
|-----------|--------|
| Network Monitoring | `wireshark`, `tshark`, `tcpdump` |
| Intrusion Detection | `zeek`, `suricata` |
| Threat Analysis | `yara`, `clamav`, `chkrootkit` |
| Containers / Sandbox | `docker`, `docker-compose` |

---

## How to Use

### 1. Download Kali Linux
Get the ISO from [Kali.org → Official Downloads](https://www.kali.org/get-kali/#kali-platforms).

### 2. Create a New VM
1. Open **VMware Workstation** → *Create a New Virtual Machine*  
2. Select the **Kali Linux 2025.3 ISO**  
3. Configure hardware:  
   - 4 GB RAM  
   - 4 Processors  
   - 30 GB Disk (NAT Networking)  
4. Boot and complete installation.

### 3. Install Tools
Once the VM is running:
```bash
git clone https://github.com/gregepierre/cyber-lab-vm.git
cd cyber-lab-vm/scripts
chmod +x install_kali_tools.sh
sudo ./install_kali_tools.sh
