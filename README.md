# 🧠 SOC Analyst Home Lab — Environment Setup

This repository documents the **setup process** for the core virtual machines required in a **SOC (Security Operations Center) Analyst Lab**.
Each section provides installation steps, configurations, and screenshots to guide you through the environment build.

---

## 🧩 Lab Overview

**Virtual Machines to Set Up:**

| Machine         | Purpose                    | OS                  |
| --------------- | -------------------------- | ------------------- |
| `DC1`           | Domain Controller          | Windows Server 2022 |
| `Win10-Client1` | Domain User Workstation    | Windows 10 Pro      |
| `Win11-Client1` | Domain User Workstation    | Windows 11 Pro      |
| `Wazuh-Server`  | SIEM & Endpoint Monitoring | Ubuntu Server 22.04 |
| `Kali-Linux`    | Attacker Machine           | Kali Linux 2024.x   |

📍 *All machines are hosted locally using VMware Workstation Pro.*

---

## ⚙️ Step 1: Install Virtualization Platform

1. Download and install **VMware Workstation Pro** (or VirtualBox).
2. Enable virtualization in your **BIOS/UEFI** settings if not already active.
3. Confirm that VMware is working properly.

📸 **Screenshot:**
![VMware Installed](https://i.imgur.com/yJZboTv.png)

---

## 🪟 Step 2: Download Operating System ISOs

Download and organize all necessary ISOs in a single folder (e.g., `CS Software`):

* [Windows Server 2022 ISO](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022)
* [Windows 10 Pro ISO](https://www.microsoft.com/software-download/windows10)
* [Windows 11 Pro ISO](https://www.microsoft.com/software-download/windows11)
* [Ubuntu Server 22.04 ISO](https://ubuntu.com/download/server)
* [Kali Linux ISO](https://www.kali.org/get-kali/)

📸 **Screenshot:**
![Downloaded ISOs](https://i.imgur.com/M3zrqjU.png)

---

## 🖥️ Step 3: Create Windows Server 2022 (Domain Controller - `DC1`)

1. Open VMware Workstation → **Create a New Virtual Machine**.
2. Choose **I will install the operating system later**.
3. OS Type: **Microsoft Windows Server 2022 (x64)**.
4. Name: `DC1`.
5. Allocate resources:

   * RAM: **4 GB**
   * CPU: **2 Cores**
   * Disk: **40 GB**
   * Network Adapter: **Host-Only**
6. Mount the **Windows Server 2022 ISO**.
7. Start installation and complete Windows setup.

📸 **Screenshot:**
![Windows Server 2022 Setup](https://i.imgur.com/yZKIOyq.png)

---

## 💻 Step 4: Create Windows 10 Client (`Win10-Client1`)

1. Create a new VM → Select **Windows 10 Pro (x64)**.
2. Name: `Win10-Client1`.
3. Allocate resources:

   * RAM: **2 GB**
   * CPU: **2 Cores**
   * Disk: **30 GB**
   * Network Adapter: **Host-Only**
4. Mount the **Windows 10 ISO**.
5. Finish setup and start installation.

📸 **Screenshot:**
![Windows 10 Setup](https://i.imgur.com/Bf1xJl8.png)

---

## 💻 Step 5: Create Windows 11 Client (`Win11-Client1`)

1. Create another VM → Select **Windows 11 Pro (x64)**.
2. Name: `Win11-Client1`.
3. Allocate:

   * RAM: **4 GB**
   * CPU: **2 Cores**
   * Disk: **40 GB**
   * Network Adapter: **Host-Only**
4. Mount the **Windows 11 ISO** and install.

📸 **Screenshot:**
![Windows 11 Setup](https://i.imgur.com/example.png)

---

## 🧱 Step 6: Create Ubuntu Server for Wazuh

1. Create a new VM → Select **Linux / Ubuntu 64-bit**.
2. Name: `Wazuh-Server`.
3. Allocate:

   * RAM: **4 GB**
   * CPU: **2 Cores**
   * Disk: **60 GB**
   * Network: **Host-Only** or **Bridged** (for easier communication).
4. Mount **Ubuntu Server 22.04 ISO** and install.

📸 **Screenshot:**
![Ubuntu Server Installation](https://i.imgur.com/example.png)

---

## 🐉 Step 7: Create Kali Linux Machine

1. Download and mount **Kali Linux ISO**.
2. Create a new VM → OS Type: **Debian / Kali Linux (64-bit)**.
3. Name: `Kali-Lab`.
4. Allocate:

   * RAM: **4 GB**
   * CPU: **2 Cores**
   * Disk: **40 GB**
   * Network Adapter: **Host-Only**.
5. Complete installation and perform initial updates:

   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

📸 **Screenshot:**
![Kali Linux Installation](https://i.imgur.com/example.png)

---

## 🌐 Step 8: Network Verification

1. Boot all VMs and verify connectivity via IP addresses.
2. Ping each machine from another to confirm the network is functioning.

   ```bash
   ping 192.168.145.101
   ```

📸 **Screenshot:**
![Network Connectivity](https://i.imgur.com/example.png)

---

## ✅ Final Setup Checklist

| Task                           | Status |
| ------------------------------ | ------ |
| VMware Installed               | ✅      |
| ISOs Downloaded                | ✅      |
| Windows Server 2022 Configured | ✅      |
| Windows 10 Client Setup        | ✅      |
| Windows 11 Client Setup        | ✅      |
| Wazuh Server Installed         | ✅      |
| Kali Linux Installed           | ✅      |
| Network Verified               | ✅      |

---

## 🧭 Next Steps

Once all systems are configured and networked, move on to:

* **Week 1:** Domain Setup & Configuration (`DC1`)
* **Week 2:** Deploying and Connecting Wazuh
* **Week 3:** Attack Simulation & Detection
* **Week 4:** Blue Team Response and Alerting

---

> 💡 **Tip:** Keep each VM snapshot after every successful configuration step so you can revert easily during lab work.

---

**Author:** Oyedele Ridwan
**Contact:** [oyedeleridwon2018@gmail.com](mailto:oyedeleridwon2018@gmail.com)
**Location:** Lagos, Nigeria
**Date:** October 2025
