# -Cybersecurity-Laboratory-Environment-Setup
Building an Isolated Virtual Laboratory for Penetration Testing and Ethical Hacking Practice
## 📌 Project Overview
This project presents the establishment of a controlled laboratory environment for practical networking and penetration-testing activities.

The setup involves installing the required file-compression utility and configuring Oracle VirtualBox to create and manage virtual machines for practical testing and experimentation.

## 🎯 Objectives

The main objectives of this lab are to:

- Prepare the computer for cybersecurity laboratory activities.
- Download and install the required supporting software.
- Set up Oracle VirtualBox for virtual machine deployment.
- Prepare the environment for future Kali Linux and cybersecurity labs.
- Take a clean VM snapshot for recovery.
- Document each stage of the laboratory setup.
- Prepare the environment for future cybersecurity projects.

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


## 🛠️ Tools Used

- Windows 10 💻
- 7-Zip 🗜️
- Oracle VirtualBox 🖥️

# 🧪 Lab Setup Procedure

## Step 1: Download 7-Zip

7-Zip was downloaded as part of the initial preparation of the
cybersecurity laboratory environment.

The Windows download page was reviewed and the appropriate installer
for a 64-bit Windows x64 system was identified.

### Screenshot

## Step 2: Launch Oracle VirtualBox

Oracle VirtualBox was opened after installation.

VirtualBox will be used as the virtualization platform for creating and
managing the virtual machines required for the cybersecurity laboratory.

### Screenshot

## Step 2: Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration: Network Name: NatNetwork IPv4 Prefix: 10.0.0.0/24 DHCP: Enabled IPv6: Disabled

### Screenshot

A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity.

This will allow future attacker and target VMs to communicate within the lab.

## Step 5. Configure the Kali Linux Network
The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

Example configuration:
> IP Address: 10.0.0.2
> Subnet Mask: 255.255.255.0
> Gateway: 10.0.0.1
> DNS: 8.8.8.8
