<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  
</p>

---

## 📌 Project Overview

This project involves building a **virtual cybersecurity and penetration-testing lab** using VirtualBox and Kali Linux.

The lab provides a controlled environment for safely practicing cybersecurity techniques, including the use of security tools, network scanning, reconnaissance, vulnerability assessment, and other penetration-testing activities.

It is configured on an isolated virtual network, allowing additional virtual machines to be integrated in the future and used as targets for authorized security testing and hands-on learning.

---


## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox.
- Install/import Kali Linux as a virtual machine.
- Create a private **NAT Network** for the cybersecurity lab.
- Configure network connectivity for Kali Linux.
- Assign a consistent IP address to the Kali VM.
- Verify network connectivity and DNS resolution.
- Take a clean VM snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.

---

## 🛡️ Purpose of the Lab

The lab offers a secure, isolated, and controlled environment for hands-on cybersecurity learning and authorized security testing.

It supports practical exercises in areas such as:

- Network reconnaissance and information gathering
- Port scanning and service identification
- Vulnerability assessment and analysis
- Network traffic and packet analysis
- Web application security testing
- Exploitation techniques in controlled lab environments
- Testing and experimenting with cybersecurity tools


## 🏗️ Lab Architecture

---

## ⚙️ Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Windows 11         |
| 🧠 Host RAM        | 8 GB               |
| ⚡ Processor       | Intel Core i5      |
| 🧰 Hypervisor      | VirtualBox 7.2  |
| 🐉 Security OS     | Kali Linux 2026.2  |
| 🧠 Kali RAM        | 2048 MB            |
| 🌐 Virtual Network | NAT Network        |
| 📡 Network Address | 10.0.0.0/24        |
| 🐧 Kali IP Address | 10.0.0.2/24        |
| 🚪 Default Gateway | 10.0.0.1           |
| 🌍 DNS Server      | 8.8.8.8            |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---

# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual machine package from its compressed `.7z` archive.

**Tool:** 7-Zip

---

## Step 2. Install VirtualBox

VirtualBox was installed to serve as the hypervisor for creating and managing virtual machines.

---

## Step 3. Create the NAT Network

A dedicated NAT network was configured in VirtualBox to provide network connectivity for the virtual machines within the lab environment.

Configuration:
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled

![](2-screenshot-network-settings-1.png)

A **NAT Network** was chosen because it allows multiple virtual machines connected to the same network to communicate with each other while maintaining outbound network access.

This configuration will support communication between future attacker and target virtual machines within the lab environment.


---

## Step 4. Import Kali Linux

The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The VM was allocated:

```text
RAM: 2048 MB
```
![](3-screenshot-kali-linux.png)
A shared folder was also configured for transferring required files between the host operating system and the Kali VM.



---

## Step 5. Import Window Server 2022

Windows Server 2022 was also imported into VirtualBox to serve as a target virtual machine within the cybersecurity lab.

The virtual machine will provide a Windows-based environment for practicing system administration, network configuration, security monitoring, vulnerability assessment, and authorized penetration-testing activities.

It will be configured to operate within the lab's virtual network, enabling communication with Kali Linux for hands-on security testing in an isolated and controlled environment.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to: NAT Network
Network:     NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop
```

The VM was allocated:

```text
RAM: 4096 MB
```
![](3-screenshot-kali-linux.png)



---


## Step 6. Configure the Kali Linux Network

The Kali Linux network settings were reviewed and configured with a static IPv4 address to ensure consistent network communication within the lab environment.

Configuration:

```text
IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

![](4-screenshot-kali-network-settings.png)

---

## Step 7. Configure the Window Server Network

The window server network settings were reviewed and configured with a static IPv4 address to ensure consistent network communication within the lab environment.

Configuration:

```text
IP Address: 10.0.0.10
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

A consistent IP address makes it easier to document the lab and reference the window machine in future exercises.

![](4-screenshot-kali-network-settings.png)

---

## Step 8. Create a Clean VM Snapshot

Once the initial configuration was complete, a snapshot of the virtual machine was created in VirtualBox to preserve its current state and provide a recovery point for future changes or troubleshooting.

Snapshot name:

```text
Kali - Network Setup
```

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.


---

# 🔎 Lab Verification

| ✅ Test                        | 🧾 Command                      | 🎯 Expected Result              |
| ----------------------------- | ------------------------------- | ------------------------------- |
| 🌐 Check Kali IP address      | `ip a`                          | Correct Kali IP displayed       |
| 🌐 Check Window IP address    | `ipconfig`                      | Correct window IP displayed     |
| 📡 Test gateway               | `ping 10.0.0.1`                 | Successful replies              |
| 🌍 Test Internet connectivity | `ping 8.8.8.8`                  | Successful replies              |
| 🔎 Test DNS resolution        | `nslookup networkwalks.com`     | Domain resolves                 |
| 🧰 Verify Nmap                | `nmap --version`                | Nmap version displayed          |
| 🔄 Verify snapshot            | Restore snapshot and run `ip a` | Baseline configuration restored |'
| Pinged window from kali       | `ping -c 4 10.0.0.10`            | Successful replies              |
| Pinged kali from window       | `ping  10.0.0.2`                 | Successful replies              |

### Results

```text
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```

```text
IP Address:
10.0.0.10/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```

---

# 🐞 Problems Encountered & Solutions

Documenting problems is an important part of the project.

## Problem 1. Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity fail  on the Kali/NetworkManager configuration.

The workaround used during this lab was:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

The network connection was then restarted/rebooted and connectivity was tested again.


---


# 💡 What I Learned

Through this project, I gained practical experience in setting up and configuring a virtualized environment for hands-on cybersecurity learning and security testing.

The key concepts and skills I gained from this project include:

### 1. NAT vs NAT Network

Standard NAT and NAT Network configurations differ in how virtual machines access and communicate over a network.

A NAT Network enables multiple virtual machines connected to the same virtual network to communicate with one another while using Network Address Translation (NAT) to access external networks.

This makes NAT Network a suitable choice for creating a multi-machine cybersecurity lab where attacker and target virtual machines need to communicate within a shared network environment.

### 2. Virtual Machine Networking

I gained an understanding of how VirtualBox network adapters connect virtual machines to different network types and how network settings influence communication between virtual machines.

### 3. Static IP Configuration

I gained practical experience configuring and verifying IPv4 addresses, subnet masks, default gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned the importance of creating a clean virtual machine snapshot **before carrying out potentially risky changes or experimental tasks**, allowing the system to be restored to a previous state when necessary.

This establishes a reliable recovery point that can be used to restore the virtual machine before future cybersecurity exercises.

### 5. Documentation

I learned the importance of documenting commands, configurations, screenshots, encountered challenges, and their solutions as part of maintaining clear and professional cybersecurity project records.

---

# 🔐 Security & Ethical Use

This laboratory is intended strictly for education purposes only.

---

# 🔗 Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)

---

# 👤 Author

**Oguntade Samuel**\
Cybersecurity Intern B084

LinkedIn: [https://www.linkedin.com/in/samuel-oguntade-604985438/](https://www.linkedin.com/in/samuel-oguntade-604985438/)

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
