# 🔵 TryHackMe - Blue

<p align="center">
  <img src="https://img.shields.io/badge/Platform-TryHackMe-red" />
  <img src="https://img.shields.io/badge/Difficulty-Easy-success" />
  <img src="https://img.shields.io/badge/OS-Windows-blue" />
  <img src="https://img.shields.io/badge/Focus-Vulnerability%20Assessment-orange" />
</p>

---

## 📖 Overview

The **Blue** room on **TryHackMe** introduces a Windows machine vulnerable to the **MS17-010 (EternalBlue)** vulnerability.

The objective of this lab is to perform host enumeration, identify vulnerable services, research publicly known vulnerabilities, obtain access within the authorized lab environment, and understand the importance of proper patch management.

> **Disclaimer:** This repository documents activities performed only inside the TryHackMe training platform for educational purposes.

---

# 🎯 Objectives

- Perform host enumeration
- Identify running services
- Research vulnerabilities
- Validate the SMB vulnerability
- Gain access to the target machine
- Explore the Windows file system
- Locate challenge flags
- Understand post-exploitation techniques

---

# 🖥️ Lab Information

| Item | Value |
|------|-------|
| Platform | TryHackMe |
| Machine | Blue |
| Operating System | Windows 7 |
| Main Service | SMB |
| Target Port | 445 |
| Vulnerability | MS17-010 (EternalBlue) |

---

# 🛠️ Tools Used

- Nmap
- Metasploit Framework
- Meterpreter
- Exploit Database
- Kali Linux

---

# 📌 Attack Methodology

```
Reconnaissance
      │
      ▼
Service Enumeration
      │
      ▼
Vulnerability Research
      │
      ▼
Exploitation
      │
      ▼
Initial Access
      │
      ▼
Post Exploitation
      │
      ▼
Flag Collection
```

---

# Phase 1 — Enumeration

The first phase focused on identifying open ports, running services, and the target operating system.

### Activities

- Host discovery
- Service detection
- SMB enumeration
- Operating system identification

### Nmap Scan

<img src="https://github.com/user-attachments/assets/fd88fce1-ff68-44b3-8dab-48d1dd4c45ac" width="100%">

---

# Phase 2 — Vulnerability Research

After identifying SMB on port **445**, research was performed to identify vulnerabilities affecting the discovered Windows version.

### Exploit Database Search

<img src="https://github.com/user-attachments/assets/6e4ea222-c3bc-461d-985d-ecb5c2e05f80" width="100%">

---

### Windows 7 SMB Research

<img src="https://github.com/user-attachments/assets/f176654f-baf7-4d32-a9c5-9452d4a9f54e" width="100%">

The investigation identified **MS17-010 (EternalBlue)** as a known vulnerability affecting unpatched Windows systems.

---

# Phase 3 — Exploitation Preparation

The exploitation framework was prepared inside the controlled lab environment.

### Launch Metasploit

<img src="https://github.com/user-attachments/assets/97349da7-c230-40a1-84c0-d81e83fe8b8b" width="100%">

---

### Search for MS17-010 Module

<img src="https://github.com/user-attachments/assets/350fd3e3-8d34-4515-a89c-e8205bf2b400" width="100%">

---

### Configure the Exploit Module

<img src="https://github.com/user-attachments/assets/2f7c4fa0-32ac-48be-8a1c-c54e2495acde" width="100%">

---

# Phase 4 — Initial Access

A Meterpreter session was successfully established after validating the exploit configuration.

### Meterpreter Session

<img src="https://github.com/user-attachments/assets/a1de532e-a7a6-4e20-90df-de2d0575dcad" width="100%">

---

# Phase 5 — Post Exploitation

After obtaining access, the Windows file system was explored to locate the required challenge flags.

---

## Locate Flag 1

<img src="https://github.com/user-attachments/assets/b1541f65-4cdc-4194-89d9-68e96cece51a" width="100%">

---

## Windows Configuration Directory

Explored:

`C:\Windows\System32\Config`

<img src="https://github.com/user-attachments/assets/5dbe4a84-ea94-492b-a5bf-3aba3ae34861" width="100%">

Purpose:

- Understand Windows registry hives
- Observe the SAM and SYSTEM files
- Explore critical operating system configuration

---

## Locate Flag 2

<img src="https://github.com/user-attachments/assets/d7613b71-d558-4186-a028-266c0887919f" width="100%">

---

## User Enumeration

Navigated through the user directories to locate the final challenge flag.

<img src="https://github.com/user-attachments/assets/ff3c3863-51d0-4fad-828e-971be008cb2c" width="100%">

---

## Locate Flag 3

<img src="https://github.com/user-attachments/assets/f2d16eda-8dcd-4b52-b4c7-d795f45124ca" width="100%">

---

# 🔒 Security Recommendations

To reduce the risk of attacks exploiting vulnerabilities such as MS17-010:

- Apply Microsoft security patches promptly.
- Disable SMBv1 where possible.
- Restrict SMB access through firewalls and network segmentation.
- Enable endpoint detection and monitoring.
- Perform regular vulnerability assessments.
- Follow the Principle of Least Privilege.

---

# 📚 Skills Demonstrated

- Network Enumeration
- Service Discovery
- Vulnerability Assessment
- Exploit Research
- Windows File System Navigation
- Meterpreter Fundamentals
- Post Exploitation
- Security Documentation

---

# 🧠 Lessons Learned

This lab improved my understanding of:

- Windows networking
- SMB vulnerabilities
- Enumeration methodology
- Vulnerability validation
- Post-exploitation concepts
- Importance of patch management
- Professional penetration testing documentation

---

# 🏷️ MITRE ATT&CK Mapping

| Technique | Description |
|------------|-------------|
| T1595 | Active Scanning |
| T1021 | Remote Services |
| T1083 | File and Directory Discovery |
| T1082 | System Information Discovery |

---

# 📂 Repository Structure

```
tryhackme-blue/
│
├── README.md
└── images/
```

---

# ⚠️ Disclaimer

This project was completed exclusively inside the **TryHackMe** learning platform. All activities were conducted in an authorized lab environment for educational purposes only.

---

# 👨‍💻 Author

## Yoganandha Namana

Cybersecurity Enthusiast • SOC Analyst Aspirant • TryHackMe Learner

- **GitHub:** https://github.com/YoganandhaNamana
- **LinkedIn:** https://www.linkedin.com/in/yoganandha-namana-aa385732b/

---

⭐ **If you found this repository useful, consider giving it a star!**
