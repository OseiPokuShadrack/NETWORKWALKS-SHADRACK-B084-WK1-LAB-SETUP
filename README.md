# NETWORKWALKS-SHADRACK-B084-WK1-LAB-SETUP
Details about my lab setup
<div align="center">

# Cybersecurity Lab Environment Setup

**Week 1 Project — NetworkWalks B084**

**Setting up a controlled virtual lab for cybersecurity learning and authorized security testing**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Cybersecurity-Lab-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/VirtualBox-v7.2.18-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2025.3-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/NetworkWalks-B084-C00000?style=flat-square" />
</p>

---
## Project Overview

This is the project details of my Week 1 cybersecurity lab setup for NetworkWalks internship.

The lab was created using **Oracle VirtualBox** and **Kali Linux 2025.3**. The purpose of this setup is to create a controlled virtual environment for cybersecurity learning, networking practice, and authorized security-testing activities.

The Kali Linux virtual machine was configured using a **NAT Network** with a consistent IPv4 address. This environment will serve as the foundation for future practical cybersecurity exercises.

## OBJECTIVES

The main objectives of this project is to:

- Install and configure Oracle VirtualBox.
- Set up Kali Linux as a virtual machine.
- Configure a NAT Network.
- Configure a static IPv4 address for Kali Linux.
- Configure the gateway and DNS server.
- Verify local gateway connectivity.
- Verify external network connectivity.
- Verify DNS resolution.
- Create a clean VirtualBox snapshot after completing the setup.
- Document the configuration, verification, and troubleshooting process.

---
##  Purpose of the Lab

The laboratory provides a controlled environment for cybersecurity learning and authorized testing.

It can later be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability-assessment practice
- Packet analysis
- Web-security testing
- Security-tool experimentation

⚠️ **Important:** This laboratory should only be used against systems that I own or have explicit permission to test.

---
#  Lab Architecture

The basic environment consists of a Windows 11 Pro host machine running Oracle VirtualBox, with Kali Linux configured as the guest operating system.

```text
┌───────────────────────────────┐
│       Windows 11 Pro Host     │
│      HP Laptop 14s-dr1xxx     │
│                               │
│       Oracle VirtualBox       │
│           7.2.18              │
│               │               │
│               ▼               │
│       ┌───────────────┐       │
│       │ Kali Linux    │       │
│       │    2025.3     │       │
│       │ 10.0.0.2/24   │       │
│       └───────┬───────┘       │
│               │               │
│          NAT Network          │
│         10.0.0.0/24           │
│               │               │
│        Gateway 10.0.0.1       │
└───────────────────────────────┘
```

---

#  Lab Configuration

## 💻 Host Machine

| Component | Configuration |
|-----------|---------------|
| Laptop | HP Laptop 14s-dr1xxx |
| Host OS | Windows 11 Pro |
| Processor | AMD Ryzen 3 PRO 3300U w/ Radeon Vega Mobile Gfx   2.10 GHz |
| Host RAM | 8 GB |
| System Type | 64-bit operating system, x64-based processor |
| Graphics | Intel(R) UHD Graphics |
| Storage | 255 GB |

## 🖥️ Virtual Lab

| Component | Configuration |
|-----------|---------------|
| Hypervisor | Oracle VirtualBox |
| VirtualBox Version | 7.2.18 r175117 |
| Security OS | Kali Linux 2025.3 |
| Virtual Network | NAT Network |
| Network Address | 10.0.0.0/24 |
| Kali IP Address | 10.0.0.2/24 |
| Default Gateway | 10.0.0.1 |
| DNS Server | 8.8.8.8 |

---

# -- Lab Setup Procedure

## Step 1. Prepare the Virtualization Environment

I installed oracle vm on my host machine and used as the virtualization platform for the Kali Linux laboratory.

### Screenshot
<img width="960" height="540" alt="Snapshot_Kali_Linux" src="https://github.com/user-attachments/assets/3bd26802-23b8-479a-afd8-beca4bd5dabb" />


---

## Step 2. Set Up Kali Linux

Kali Linux 2025.3 was configured as the guest operating system inside VirtualBox.

The virtual machine was prepared as the main workstation for the laboratory.

---

## Step 3. Configure the NAT Network

A NAT Network was used to provide networking for the virtual laboratory.

The lab network was configured with the following settings:

| Setting | Value |
| --- | --- |
| Network Type | NAT Network |
| Network Address | 10.0.0.0/24 |
| Gateway | 10.0.0.1 |

The NAT Network allows the Kali Linux virtual machine to communicate with the gateway and access external network resources while keeping the laboratory environment separated from the host network.

### Network Configuration

```text
Network: 10.0.0.0/24
Gateway: 10.0.0.1
```
### Screenshot

<img width="960" height="540" alt="NatNetwork_Setup" src="https://github.com/user-attachments/assets/79dea473-7690-482c-8ea5-9c3091694bab" />

---

## Step 4. Configure the Static IPv4 Address

The Kali Linux virtual machine was configured with a static IPv4 address to keep the network configuration consistent during the laboratory exercises.

The IPv4 settings were configured as follows:

| Setting | Value |
| --- | --- |
| IPv4 Method | Manual |
| IP Address | 10.0.0.2 |
| Netmask | 24 |
| Gateway | 10.0.0.1 |
| DNS Server | 8.8.8.8 |

The static IP configuration was applied using the Network Connections settings in Kali Linux.

### Screenshot

<img width="1536" height="708" alt="Kali_network_Settings" src="https://github.com/user-attachments/assets/405430e5-47e5-4231-ab74-e12c76588d9c" />


## Step 5. Verify the Lab Network

After configuring the network, several commands were used to verify the setup.

### Check the Kali IP Address

```bash
ip addr
```
Note: Make sure the ip is exactly 10.0.0.2 as the in the settings
The `eth0` must show:

```text
10.0.0.2/24
```

### Test External Connectivity

```bash
ping 8.8.8.8
```

### Screenshot

<img width="4400" height="2029" alt="Internet Access" src="https://github.com/user-attachments/assets/7b43e57b-0193-4c87-9aa1-5a69617dc708" />


This confirmed connectivity between Kali Linux and the configured gateway.

## Step 6. Create a Virtual Machine Snapshot

After completing the Kali Linux configuration and network verification, a snapshot was created in VirtualBox.

The snapshot is the restore point for the cybersecurity laboratory.

### Snapshot Details

| Setting | Value |
| --- | --- |
| Snapshot Name | My Fresh Kali Linux |
| Status | Kali VM powered off |
| Purpose | Restore point for the verified lab environment |

The snapshot was created after verifying the static IP address, gateway connectivity and internet connectivity

This allows the virtual machine to be restored to a known working state if any configuration changes cause problems during future laboratory exercises.

### Screenshot

<img width="960" height="540" alt="Snapshot_Kali_Linux" src="https://github.com/user-attachments/assets/7c3baf1a-aa0a-4572-9ee1-5e4663cf88d9" />

---

## Lab Verification Summary

The following checks were completed successfully:

| Verification | Result |
| --- | --- |
| Kali IP Address | 10.0.0.2/24 |
| Gateway Connectivity | Successful |
| Internet Connectivity | Successful |
| Virtual Machine Snapshot | Created |

The laboratory environment was successfully configured and verified for cybersecurity training activities.

---

## Problems Encountered & Solutions

During the lab setup, a few internet connectivity issues were encountered and resolved.

### 1. IP assignment issues leading to internet connectivity failure

**Solution:**  
I used these three prompts provided by our instructor
1. sudo nmcli connection modify "Wireless Connection 1" ipv4.dad-timeout 0
2. sudo nmcli connection down "Wired Connection 1"
3. sudo nmcli connection up "Wired Connection 1" 

## What I Learned

Through this lab setup, I learned how to:

- Install and configure Kali Linux in VirtualBox.
- Configure a NAT Network for a virtual cybersecurity laboratory.
- Assign a static IPv4 address to a Kali Linux virtual machine.
- Configure the gateway and DNS settings.
- Verify network connectivity using ping.
- Create a VirtualBox snapshot for restoring the lab environment.
- Troubleshoot basic network configuration issues.

This lab provided practical experience in preparing a controlled environment for future cybersecurity exercises.

---

## Security & Ethical Use

This cybersecurity laboratory was created only for educational purposes and authorized security testing.

All activities were performed within the controlled virtual lab environment. Any scanning, testing, or security-related activity should only be conducted on systems and networks where proper permission has been provided.

The lab environment helps provide a safe and isolated setup for learning cybersecurity concepts without affecting unauthorized systems.

---

## Tools & Resources

### Tools Used

- Oracle VirtualBox
- Kali Linux 2025.3
- Windows 11 Pro
- NetworkManager
- `ping`

### Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)



---

## Author

**Shadrack Osei Poku**

Cybersecurity Intern — NetworkWalks  
Batch: **B084**
LinkedIn: [Shadrack Osei Poku](https://www.linkedin.com/in/shadrack-osei-poku-35b297387/)

---

##  Project Overview

**Program Name:** Cybersecurity at NetworkWalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
