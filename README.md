# -Cybersecurity-Laboratory-Environment-Setup
**Building an Isolated Virtual Laboratory for Penetration Testing and Ethical Hacking Practice**

---
## 📌 Project Overview
This project presents the establishment of a controlled laboratory environment for practical networking and penetration-testing activities.

The setup involves installing the required file-compression utility and configuring Oracle VirtualBox to create and manage virtual machines for practical testing and experimentation.

---
## 🎯 Objectives

The main objectives of this lab are to:

- Prepare the computer for cybersecurity laboratory activities.
- Download and install the required supporting software.
- Set up Oracle VirtualBox for virtual machine deployment.
- Prepare the environment for future Kali Linux and cybersecurity labs.
- Take a clean VM snapshot for recovery.
- Document each stage of the laboratory setup.
- Prepare the environment for future cybersecurity projects.

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

⚠️ Important: This laboratory must only be used for systems that you own or have explicit permission to test. Do not use the lab or its tools to attack unauthorized systems.

---
## ⚙️ Lab Configuration

|🧩 Component|⚙️ Configuration|
|---|---|
|🖥️ Host OS  |💻 Windows 10   |
|🧠 Host RAM |8 GB |  
| ⚡ Processor | Celeron (R) |
| 🧰 Hypervisor | VirtualBox 7.2 |
| 🐉 Security OS | Kali Linux 2026.2 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Virtual Network | NAT Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |

---
## 🛠️ Tools Used

- Windows 10 💻
- 7-Zip 🗜️
- Oracle VirtualBox 🖥️

---
# 🧪 Lab Setup Procedure

## Step 1: Download 7-Zip

7-Zip was downloaded as part of the initial preparation of the
cybersecurity laboratory environment.

The Windows download page was reviewed and the appropriate installer
for a 64-bit Windows x64 system was identified.

![7-Zip Installer](https://github.com/Patrick-Adie24/-Cybersecurity-Laboratory-Environment-Setup/blob/main/screenshots01-7zip-download.png.png?raw=true)

## Step 2: Launch Oracle VirtualBox

Oracle VirtualBox was opened after installation.

VirtualBox will be used as the virtualization platform for creating and
managing the virtual machines required for the cybersecurity laboratory.

![Oracle Virtualbox](https://github.com/Patrick-Adie24/-Cybersecurity-Laboratory-Environment-Setup/blob/main/screenshots02-virtualbox-manager.png.png?raw=true)

## Step 3: Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled

![NAT Network Setting](https://github.com/Patrick-Adie24/-Cybersecurity-Laboratory-Environment-Setup/blob/main/screenshot-network03-%20NAT%20settings-1.png.png?raw=true)

A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.

## Step 4. Import Kali Linux
The Kali Linux virtual machine was downloaded from the official Kali Linux website and imported into VirtualBox.

![Kali-nux](https://github.com/Patrick-Adie24/-Cybersecurity-Laboratory-Environment-Setup/blob/main/screenshot04-kali-linux.png.png?raw=true)

The VM network adapter was configured as follows:

> Adapter 1
> 
> Attached to:NAT Network
> 
> Network:NatNetwork
>
> Adapter Type: Intel PRO/1000 MT Desktop

![Kali-Vm-Network-Adapter](https://github.com/Patrick-Adie24/-Cybersecurity-Laboratory-Environment-Setup/blob/main/Screenshot05-VM%20network-adapter.png.png?raw=true)

The VM was allocated:
> RAM: 2048 MB

## Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:
> IP Address: 10.0.0.2
> 
> Subnet Mask: 255.255.255.0
>
> Gateway: 10.0.0.1
>
> DNS: 8.8.8.8

A consistent IP address makes it easier to document the lab and reference the Kali machine in future exercises.

### Screenshot

## Step 6. Create a Clean VM Snapshot
After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

> Clean Kali - Network Setup

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.

---
# 🔎 Lab Verification

|✅ Test	|🧾 Command	|🎯 Expected Result|
|---|---|---|
|🌐 Check IP address	| > ip a ifconfig eth0	|Correct Kali IP displayed|
|🌍 Test Internet connectivity	|ping 8.8.8.8	|Successful replies|
|🔄 Verify snapshot	|Restore snapshot and run > ip a 	|Successful replies|

### Screenshot

---
# 🐞 Problems Encountered & Solutions
## Problem 1. Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity may fail depending on the Kali/NetworkManager configuration.

One workaround used during this lab was:
> sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

The network connection was then restarted/rebooted and connectivity was tested again.

---
# 📚 What I Learned
During this stage of the project, I learned:

**1. Installation of 7-ZIP Installer**
   This provides a known-good recovery point for future cybersecurity exercises.- How to identify the appropriate 7-Zip installer for Windows. 

**2. NAT vs NAT Network**
A standard NAT configuration and a NAT Network serve different purposes.
A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

**4. Virtual Machine Networking**
I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

**5. Static IP Configuration**
I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

---
**6. VM Snapshots**
I learned that a clean snapshot should be created before performing risky or experimental activities.

7. The importance of documenting each stage of a technical project.

---
# 🔐 Security & Ethical Use
This laboratory is intended strictly for education purposes only.

---
# 🔗 Resources
- 7-Zip: https://7-zip.org/download.html
- VirtualBox: https://virtualbox.org/wiki/Downloads
- Kali Linux: https://kali.org/get-kali

---
# 👤 Author
**ADIE PATRICK BETIANG**

Cybersecurity Professional B083

*LinkedIn*:www.linkedin.com/in/patrick-adie-552840267
---

# 📌 Project Information
**Program Name:** 
Cybersecurity at Networkwalks | Week: 01 | Project: Cybersecurity & Pentesting Lab Setup 
**Repository:** GitHub
