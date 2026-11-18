<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building an isolated virtual lab for penetration testing and ethical hacking practice**
</div>


---

## 📌 Project Overview

This project focuses on setting up a **virtual cybersecurity and penetration-testing laboratory** using VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

---

## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox as the hypervisor.
- Install and import Kali Linux as a dedicated virtual machine.
- Create a private **NAT Network** for the cybersecurity lab.
- Configure network connectivity for Kali Linux.
- Assign a consistent static IP address to the Kali VM.
- Verify network connectivity, gateway routing, and DNS resolution.
- Take a clean VM snapshot for baseline recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity exercises.

---

## 🛡️ Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Exploitation practice
- Security-tool experimentation

⚠️ **Important:** This laboratory must only be used for systems that you own or have explicit permission to test. Do not use the lab or its tools to attack unauthorized systems.

---

## 🏗️ Lab Architecture

<p align="center">
  <img width="1366" height="768" alt="Lab Architecture" src="https://github.com/user-attachments/assets/355a55e3-c31e-4021-a1bc-a55cb0393848" />
</p>

Additional target machines can be added to the same virtual network in future projects.

---

## ⚙️ Lab Configuration

| 🧩 Component       | ⚙️ Configuration   |
| ------------------ | ------------------  |
| 🖥️ Host OS         | Windows 11 Home    |
| 🧠 Host RAM        | 8 GB               |
| ⚡ Processor       | 2 vCPUs Allocated  |
| 🧰 Hypervisor      | VirtualBox 7.2.14  |
| 🐉 Security OS     | Kali Linux 2026.3  |
| 🧠 Kali RAM        | 4096 MB (4 GB)     |
| 💾 Kali Storage    | 20 GB SSD          |
| 🌐 Virtual Network | NAT Network        |
| 📡 Network Address | 10.0.0.0/24        |
| 🐧 Kali IP Address | 10.0.0.2/24        |
| 🚪 Default Gateway | 10.0.0.1           |
| 🌍 DNS Server      | 8.8.8.8            |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

---

# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

7-Zip was installed to extract compressed archive packages, including the Kali Linux virtual machine images and installation files.

**Tool:** 7-Zip

---

## Step 2. Install VirtualBox & Hypervisor Setup

VirtualBox 7.2.14 was installed as the hypervisor. Hardware virtualization (Intel VT-x / AMD-V and Nested Paging) was verified in the system firmware/BIOS and enabled within the hypervisor settings.

Configuration details:
- **CPU:** 2 virtual processors
- **Memory:** 4 GB RAM allocated
- **Storage:** 20 GB SSD storage

<p align="center">
  <img width="772" height="512" alt="VirtualBox Hardware Virtualization Settings" src="https://github.com/user-attachments/assets/32af197b-981e-47bc-99d1-e44704573e34" />
</p>

---

## Step 3. Create the NAT Network

A dedicated NAT Network was created in VirtualBox to isolate the lab environment.

Configuration:
```text
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled
```

<p align="center">
  <img width="1366" height="768" alt="VirtualBox NAT Network Settings" src="https://github.com/user-attachments/assets/3764a439-eec3-4abd-8867-4438cc496043" />
</p>

A **NAT Network** was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This allows future attacker and target VMs to communicate seamlessly within the lab.

---

## Step 4. Import & Configure Kali Linux

The Kali Linux virtual machine was obtained from the official source and configured inside VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1:
Attached to:      NAT Network
Network Name:     NatNetwork
Adapter Type:     Intel PRO/1000 MT Desktop (82540EM)
Promiscuous Mode: Allow All
Cable Connected:  Checked
```

<p align="center">
  <img width="648" height="515" alt="Kali Linux Network Adapter Settings" src="https://github.com/user-attachments/assets/f169d741-1689-442d-9863-ae7b6d83f8d5" />
</p>

The VM was allocated 4096 MB of RAM and 2 vCPUs. A shared folder (`Downloads`) was also configured for transferring required files between the Windows host operating system and the Kali VM.

<p align="center">
  <img width="1366" height="768" alt="Kali Linux VM Environment" src="https://github.com/user-attachments/assets/e7596513-034c-4929-ac46-9e01f901b70f" />
</p>

---

## Step 5. Configure the Kali Linux Network

The Kali Linux network interface was checked and configured with a consistent IPv4 static address.

Example configuration:

```text
IP Address:  10.0.0.2
Subnet Mask: 255.255.255.0 (/24)
Gateway:     10.0.0.1
DNS:         8.8.8.8
```

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

<p align="center">
  <img width="695" height="491" alt="Kali Linux Static IPv4 Network Configuration" src="https://github.com/user-attachments/assets/28b1f6a4-9b63-4704-bc16-c1211168723e" />
</p>

---

## Step 6. Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created to establish a baseline.

Snapshot details:
```text
Snapshot Name: fresh kali installation
Description:   the networkwalks journey, i have set ipv4 settings and made sure internet is working
```

The snapshot represents the clean baseline of the laboratory. If a future exercise changes or damages the VM configuration, the machine can be restored quickly to this baseline.

<p align="center">
  <img width="1366" height="768" alt="VirtualBox Snapshot Creation" src="https://github.com/user-attachments/assets/e04e330b-73ec-4b53-ba8b-c14a07281098" />
</p>

<p align="center">
  <img width="1366" height="768" alt="Baseline Snapshot Saved" src="https://github.com/user-attachments/assets/2cb0e754-2d4b-4bce-951c-fa56f2acd062" />
</p>

---

# 🔎 Lab Verification

| ✅ Test                        | 🧾 Command                      | 🎯 Expected Result              |
| ----------------------------- | ------------------------------- | ------------------------------- |
| 🌐 Check IP address           | `ip a`                          | Correct Kali IP displayed       |
| 🛣️ Check routing table        | `ip route`                      | Default gateway via 10.0.0.1    |
| 📡 Test gateway               | `ping -c 4 10.0.0.1`            | Successful replies              |
| 🌍 Test Internet connectivity | `ping -c 4 8.8.8.8`             | Successful replies              |
| 🔎 Test DNS resolution        | `nslookup networkwalks.com`     | Domain resolves                 |
| 🧰 Verify Nmap                | `nmap --version`                | Nmap version displayed          |
| 🔄 Verify snapshot            | Restore snapshot and run `ip a` | Baseline configuration restored |

### Verification Commands & Results

```bash
# Verify IP address configuration
ip a

# Verify routing table and default gateway
ip route

# Test reachability to the default gateway
ping -c 4 10.0.0.1

# Test DNS name resolution
nslookup networkwalks.com
```

```text
IP Address:  10.0.0.2/24
Gateway:     10.0.0.1
DNS Server:  8.8.8.8
Status:      Connected & Active
```

<p align="center">
  <img width="715" height="476" alt="Lab Verification in Kali Linux Terminal" src="https://github.com/user-attachments/assets/463f49ca-4212-4739-81f7-0cbc3b9b6a60" />
</p>

---

# 🐞 Problems Encountered & Solutions

Documenting problems is an important part of the project.

## Problem 1. Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity may fail depending on the Kali/NetworkManager configuration.

One workaround used during this lab was:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

The network connection was then restarted/rebooted and connectivity was tested again.

> **Important:** Network interface and connection names may differ between systems. Verify your actual connection name using `nmcli connection show` before running the command.

---

## Problem 2. VirtualBox VT-x / Virtualization Error

The VM initially failed to start because hardware virtualization was disabled in the system firmware/BIOS.

The issue was resolved by:

1. Restarting the computer.
2. Entering BIOS/UEFI settings.
3. Enabling Intel VT-x / AMD-V hardware virtualization.
4. Saving the configuration.
5. Restarting the computer.
6. Starting the Kali VM again.

After enabling virtualization, the VM started successfully.

---

# 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking

I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3. Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned that a clean snapshot should be created **before performing risky or experimental activities**.

This provides a known-good recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

---

# 🔐 Security & Ethical Use

This laboratory is intended strictly for education purposes only. All testing must be conducted in an isolated, private virtual environment or on systems where explicit written authorization has been granted.

---

# 🔗 Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)
- **NetworkWalks Academy:** [https://networkwalks.com/](https://networkwalks.com/)

---

# 👤 Author

**Vaina Moshi**\
Cybersecurity Professional | Batch B084

GitHub: [https://github.com/Vaina-source](https://github.com/Vaina-source)

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Batch:** B084 | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
