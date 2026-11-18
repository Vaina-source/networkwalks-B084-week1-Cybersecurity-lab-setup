# Cybersecurity Lab Environment Setup

## Project overview

This project documents the setup of an isolated virtual cybersecurity learning lab using [VirtualBox/ version 7.2.14] and [kali-linux-2026.3-vmware-amd64]. The lab is intended for practicing security concepts in a controlled environment that I own or am explicitly authorized to use.

The goal was to build a repeatable foundation for future defensive and security-testing exercises. This repository records the configuration process, verification steps, screenshots, challenges, and lessons learned.

## Objectives

- Install and configure a hypervisor for virtual machines.
- Import or install a cybersecurity-focused Linux virtual machine.
- Configure a private virtual network for the lab.
- Check the virtual machine's network settings and connectivity.
- Verify that DNS resolution works, where applicable.
- Create a clean recovery point or snapshot, if completed.
- Document the work clearly so the environment can be rebuilt or troubleshot.

## Lab scope and authorized use

This is an educational lab. I will use it only on systems that I own or for which I have explicit written authorization. I will not scan, access, or test public, workplace, school, or third-party systems without permission and a defined scope.

## Components

- **Host operating system:** [window 11 home]
- **Hypervisor:** [VirtualBox/ version 7.2.14]
- **Guest operating system:** [kali-linux-2026.3-vmware-amd64]]
- **Virtual network mode:** [NAT / NAT Network /]
- **Virtual machine resources:** [RAM / CPU]

## Setup steps

### 1. Prepare the virtualization software

I installed and opened **[VirtualBox/ version 7.2.14]**, then checked that hardware virtualization was enabled where required. I configured the virtual machine with • CPU: The number of virtual processors was 2 CPUs
                                    • Memory: The amount of RAM allocated was 4GB of RAM 
                                    • Storage: The size and type of the virtual hard drive was 20GB of SSD storage


### 2. Install or import the guest operating system

I obtained kali linux from its official source and installed it into the hypervisor. I checked that the VM starts successfully and recorded the relevant settings.

### 3. Configure the lab network

I created or selected a NAT network for the lab and attached the guest VM to it. This keeps the lab configuration separate from unrelated systems. Describe your actual topology here, and do not include real public IP addresses or sensitive network details.

### 4. Configure and verify networking

I checked the guest's network interface and confirmed the expected addressing and connectivity for this lab. I used commands such as the following only within my own lab:

```bash
ip a
ip route
ping -c 4 <your-lab-gateway>    
nslookup <test-domain>






/home/vaina/Pictures/Screenshot_2026-11-18_12_47_26.png

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/355a55e3-c31e-4021-a1bc-a55cb0393848" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/3764a439-eec3-4abd-8867-4438cc496043" />

<img width="695" height="491" alt="image" src="https://github.com/user-attachments/assets/28b1f6a4-9b63-4704-bc16-c1211168723e" />

<img width="648" height="515" alt="image" src="https://github.com/user-attachments/assets/f169d741-1689-442d-9863-ae7b6d83f8d5" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e7596513-034c-4929-ac46-9e01f901b70f" />

<img width="772" height="512" alt="image" src="https://github.com/user-attachments/assets/32af197b-981e-47bc-99d1-e44704573e34" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e04e330b-73ec-4b53-ba8b-c14a07281098" />

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/2cb0e754-2d4b-4bce-951c-fa56f2acd062" />

<img width="715" height="476" alt="image" src="https://github.com/user-attachments/assets/463f49ca-4212-4739-81f7-0cbc3b9b6a60" />

