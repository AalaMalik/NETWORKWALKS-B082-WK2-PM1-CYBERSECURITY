<div align="center">

# 🔍 Footprinting & Network Scanning Lab

**Passive Reconnaissance with GHDB & Active Network Discovery using Zenmap**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Reconnaissance-GHDB-E87500?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Scanner-Zenmap%20%2F%20Nmap-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Skill-Footprinting-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Target%20Subnet-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Platform-Windows%2010-0070C0?style=flat-square&labelColor=000000&logo=windows&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-Week%2002-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000" />
</p>

---

## 📌 Project Overview

This project encompasses two core phases of information gathering and enumeration within cybersecurity: **Passive Footprinting via Google Hacking Database (GHDB)** and **Active Network Scanning via Zenmap**.

- **Module 2 (PM2):** Leverages GHDB dorks on Exploit-DB to discover publicly exposed assets (such as live camera interfaces and open index directories) without directly contacting the target hosts.
- **Module 5 (PM5):** Focuses on local subnet discovery, ping sweeps, MAC address resolution, and topology visualization using Zenmap (the official GUI frontend for Nmap) on a Windows platform.

---

## 🎯 Objectives

- Navigate and extract Google Dorks from the **Exploit-DB GHDB repository**.
- Execute advanced search queries to identify live exposed IoT devices and open document repositories.
- Install and configure **Zenmap & Npcap** on Windows.
- Identify local host IP configuration and LAN subnet boundaries.
- Execute non-intrusive ping scans (`nmap -sn`) to discover live hosts and their MAC addresses.
- Export, review, and document network topology maps in graphic and PDF formats.

---

## 🛡️ Tools & Lab Environment

| 🧩 Component | ⚙️ Details |
| :--- | :--- |
| **Operating System** | Windows 10 |
| **Passive Recon Source** | Google Hacking Database (Exploit-DB) |
| **Scanning Utility** | Zenmap / Nmap 7.91 (with Npcap 1.00) |
| **Command Utilities** | Windows Command Prompt (`ipconfig`) |
| **Target Local Subnet** | `10.0.0.0/24` |
| **Scan Profile** | Ping Scan (`nmap -sn`) |

---

# 🪜 Project Module 2 (PM2): Footprinting & Reconnaissance with GHDB

GHDB uses advanced Google search operators to query indexed information that was unintentionally left public. Because search requests are served entirely by Google’s cache and index, the target server is never directly probed.

### Step 1. Access the Exploit-DB GHDB Repository
1. Navigate to `https://www.exploit-db.com`.
2. Select **GHDB** from the left-hand navigation pane.

![](pm2-step1-ghdb-menu.png)

---

### Step 2. Locate Vulnerable Camera Dorks
Search for keywords such as `cam` in the quick search bar to filter dorks categorised under **Various Online Devices** or **Pages Containing Login Portals**.

![](pm2-step2-ghdb-cam-search.png)

---

### Step 3. Execute Dork & Verify Exposed Feeds
Copy the desired dork and execute the query on Google.

```text
intitle:"webcamXP" inurl:8080
