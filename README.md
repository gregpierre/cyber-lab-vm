# Cyber Lab VM — Starter (Kali on VMware)

**VM name:** Cybersecurity Lab  
**Guest OS:** Kali Linux 2025.3 — https://www.kali.org/get-kali/#kali-platforms  
**Hypervisor:** VMware Workstation (Windows)

This repository contains reproducible instructions and a provisioning script to set up a Kali-based cyber lab that supports both **offensive** and **defensive** exercises.
> **Important:** This repo does NOT include the VM image. It contains the steps and scripts to recreate the environment locally.

---

## Quick Start (prerequisites)
1. Install **VirtualBox** or use VMware Workstation (you already use VMware) and install **Vagrant** if you want to use a Vagrant workflow. The scripts are written for Debian-based systems (Kali).
2. Download the Kali ISO from: https://www.kali.org/get-kali/#kali-platforms and install it as a VM named **Cybersecurity Lab**.
3. Apply the VM settings you prefer (example: 4 CPUs, 4 GB RAM, 30 GB disk, NAT networking).
4. Copy this repo into the VM or clone it from your GitHub after uploading.

### Quick commands (once inside the VM)
```bash
# Update & upgrade
sudo apt update && sudo apt -y full-upgrade

# Run the installer script from this repo
chmod +x scripts/install_kali_tools.sh
sudo scripts/install_kali_tools.sh
```

---

## What the installer installs (offensive + defensive)
**Offensive / Red-team tools** (examples)
- nmap, gobuster, masscan, hydra, wafw00f
- metasploit-framework (package)
- sqlmap, nikto

**Defensive / Blue-team tools**
- wireshark, tshark, suricata, zeek (if available), elastic-agent (optional)
- osquery (optional), syslog / rsyslog, logrotate

**Common tooling & utilities**
- git, curl, python3, pip, docker (optional), tcpdump, net-tools, seclists

> The installer is idempotent and will skip already-installed packages. Heavy installs (full Metasploit, Elastic Stack) are optional/conditional to avoid long unattended installs.

---

## Structure of this starter repo
```
cyber-lab-vm/
├─ README.md
├─ .gitignore
├─ scripts/
│  └─ install_kali_tools.sh
└─ docs/
   └─ vm-settings.png   <-- copy your VMware screenshot here (already included)
```

## Safety & ethics
- **Only** run offensive tooling in isolated lab networks. Do not target external systems or networks you do not own/have permission to test.
- Use sanitized PCAPs or synthetic data when sharing outputs.

## How to share the actual VM (optional)
If you want to share a VM image (OVA), host it outside of GitHub (S3, Google Drive) and link to it in this repo do **not** upload large VM images to GitHub directly.

---
If you'd like, I can also create a GitHub Actions workflow that lints the repo and validates script syntax.  
