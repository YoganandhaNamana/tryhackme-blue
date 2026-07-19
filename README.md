# 🔵 TryHackMe - Blue

![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy-success)
![Category](https://img.shields.io/badge/Category-Windows-blue)
![Focus](https://img.shields.io/badge/Focus-Vulnerability%20Assessment-orange)

## 📖 Overview

The **Blue** room on TryHackMe introduces a Windows machine vulnerable to **MS17-010 (EternalBlue)**. The objective of this lab is to practice identifying exposed services, researching known vulnerabilities, gaining access to the target, and performing basic post-exploitation tasks in a safe, controlled environment.

> **Note:** This repository documents my learning process and methodology. It does not provide instructions for attacking systems outside authorized lab environments.

---

# 🎯 Objectives

- Perform host enumeration
- Identify exposed network services
- Research known vulnerabilities
- Validate the presence of the SMB vulnerability
- Gain access to the target in the lab environment
- Explore the Windows file system
- Locate challenge flags
- Understand the importance of patch management

---

# 🖥️ Lab Environment

| Component | Details |
|-----------|---------|
| Platform | TryHackMe |
| Operating System | Windows 7 |
| Service | SMB |
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
Exploit Selection
        │
        ▼
Initial Access
        │
        ▼
Post Exploitation
        │
        ▼
System Exploration
        │
        ▼
Flag Collection
```

---

# Phase 1 — Enumeration

The first step was identifying available network services.

### Activities

- Performed service detection
- Enumerated SMB service
- Identified Windows operating system
- Observed exposed RPC services

### Screenshot

```
images/nmap-scan.png
```

---

# Phase 2 — Vulnerability Research

After discovering SMB on port 445, I researched publicly documented vulnerabilities affecting the identified operating system.

The investigation highlighted **MS17-010 (EternalBlue)** as a significant vulnerability associated with unpatched Windows systems.

### Screenshots

```
images/exploitdb-search.png

images/windows7-search.png
```

---

# Phase 3 — Exploitation Preparation

The next phase involved preparing the exploitation framework within the lab environment.

Tasks completed:

- Started Metasploit Framework
- Located the appropriate exploit module
- Reviewed required configuration options
- Prepared the exploitation module

### Screenshots

```
images/msfconsole.png

images/search-ms17.png

images/module-options.png
```

---

# Phase 4 — Initial Access

After validating the configuration, a shell session was established against the target machine inside the TryHackMe environment.

The session was later upgraded to **Meterpreter**, enabling enhanced interaction with the compromised system.

### Screenshot

```
images/meterpreter-session.png
```

---

# Phase 5 — Post Exploitation

With elevated access available, the Windows file system was explored.

The objectives included:

- Inspecting system directories
- Exploring user directories
- Understanding Windows configuration files
- Locating challenge flags

---

## Flag 1

Located within the root directory.

Screenshot

```
images/flag1.png
```

---

## Windows Configuration

Explored:

```
C:\Windows\System32\Config
```

Purpose:

- Observe Windows registry hives
- Understand SAM and SYSTEM storage locations

Screenshot

```
images/system32-config.png
```

---

## Flag 2

Located during exploration of Windows configuration files.

Screenshot

```
images/flag2.png
```

---

## User Enumeration

Navigated through user directories to understand the Windows file structure.

Screenshot

```
images/user-documents.png
```

---

## Flag 3

Located within the user's Documents directory.

Screenshot

```
images/flag3.png
```

---

# 🔒 Security Recommendations

The vulnerable system demonstrates why timely security updates are critical.

Recommended defensive measures include:

- Apply Microsoft security updates promptly.
- Disable SMBv1 where possible.
- Restrict SMB access using network segmentation.
- Enable endpoint protection.
- Monitor SMB activity using intrusion detection systems.
- Conduct regular vulnerability assessments.
- Limit administrative privileges following the principle of least privilege.

---

# 📚 Skills Demonstrated

- Network Enumeration
- Service Identification
- Vulnerability Assessment
- Exploit Research
- Windows File System Navigation
- Meterpreter Usage
- Post Exploitation
- Security Analysis
- Documentation

---

# 🧠 Lessons Learned

This lab strengthened my understanding of:

- Windows service enumeration
- SMB security risks
- Vulnerability research methodology
- Controlled exploitation within authorized environments
- Windows directory structure
- Importance of patch management
- Documentation of penetration testing activities

---

# 🏷️ MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1595 | Active Scanning |
| T1190 | Exploit Public-Facing Application (lab context) |
| T1021 | Remote Services |
| T1083 | File and Directory Discovery |
| T1082 | System Information Discovery |

---

# 📂 Repository Structure

```
tryhackme-blue/
│
├── README.md
│
├── images/
│   ├── nmap-scan.png
│   ├── exploitdb-search.png
│   ├── windows7-search.png
│   ├── msfconsole.png
│   ├── search-ms17.png
│   ├── module-options.png
│   ├── meterpreter-session.png
│   ├── flag1.png
│   ├── system32-config.png
│   ├── flag2.png
│   ├── user-documents.png
│   └── flag3.png
│
└── LICENSE
```

---

# ⚠️ Disclaimer

This repository documents activities performed exclusively within the **TryHackMe** training platform. All testing was conducted in an authorized laboratory environment for educational purposes only. The techniques discussed should never be used against systems without explicit permission.

---

## 👨‍💻 Author

**Yoganandha Namana**

Cybersecurity Enthusiast | SOC Analyst Aspirant | TryHackMe Learner

- GitHub: *Add your GitHub profile link here*
- LinkedIn: *Add your LinkedIn profile link here*
