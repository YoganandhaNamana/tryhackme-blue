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

<img width="1291" height="468" alt="nmap scan" src="https://github.com/user-attachments/assets/fd88fce1-ff68-44b3-8dab-48d1dd4c45ac" />


```


# Phase 2 — Vulnerability Research

After discovering SMB on port 445, I researched publicly documented vulnerabilities affecting the identified operating system.

The investigation highlighted **MS17-010 (EternalBlue)** as a significant vulnerability associated with unpatched Windows systems.

### Screenshots


```
<img width="1907" height="951" alt="Search exploit DB and go to search EDB" src="https://github.com/user-attachments/assets/6e4ea222-c3bc-461d-985d-ecb5c2e05f80" />


<img width="1917" height="973" alt="Search Windows 7 and port number 445" src="https://github.com/user-attachments/assets/f176654f-baf7-4d32-a9c5-9452d4a9f54e" />


```

# Phase 3 — Exploitation Preparation

The next phase involved preparing the exploitation framework within the lab environment.

Tasks completed:

- Started Metasploit Framework
- Located the appropriate exploit module
- Reviewed required configuration options
- Prepared the exploitation module

### Screenshots

```
<img width="1042" height="708" alt="metasploit msfconsole" src="https://github.com/user-attachments/assets/97349da7-c230-40a1-84c0-d81e83fe8b8b" />
images/msfconsole.png

<img width="1901" height="726" alt="search ms17" src="https://github.com/user-attachments/assets/350fd3e3-8d34-4515-a89c-e8205bf2b400" />


<img width="1907" height="666" alt="set sessoin 1" src="https://github.com/user-attachments/assets/6b65ce71-0be4-4654-b493-f971b30203ff" />

<img width="1581" height="650" alt="use 0" src="https://github.com/user-attachments/assets/2f7c4fa0-32ac-48be-8a1c-c54e2495acde" />

```

---

# Phase 4 — Initial Access

After validating the configuration, a shell session was established against the target machine inside the TryHackMe environment.

The session was later upgraded to **Meterpreter**, enabling enhanced interaction with the compromised system.

### Screenshot

```
<img width="1907" height="666" alt="set sessoin 1" src="https://github.com/user-attachments/assets/a1de532e-a7a6-4e20-90df-de2d0575dcad" />
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
<img width="1883" height="655" alt="Finding flag 1 path" src="https://github.com/user-attachments/assets/b1541f65-4cdc-4194-89d9-68e96cece51a" />
```

---

## Windows Configuration

Explored:

```
<img width="1897" height="615" alt="cd windows -system32-config" src="https://github.com/user-attachments/assets/5dbe4a84-ea94-492b-a5bf-3aba3ae34861" />
```

Purpose:

- Observe Windows registry hives
- Understand SAM and SYSTEM storage locations

---

## Flag 2

Located during exploration of Windows configuration files.

Screenshot

```
<img width="1900" height="355" alt="flage 2" src="https://github.com/user-attachments/assets/d7613b71-d558-4186-a028-266c0887919f" />

## User Enumeration

Navigated through user directories to understand the Windows file structure.

Screenshot

<img width="1890" height="491" alt="finding flag 3 path" src="https://github.com/user-attachments/assets/ff3c3863-51d0-4fad-828e-971be008cb2c" />
```

---

## Flag 3

Located within the user's Documents directory.

Screenshot

```
<img width="1422" height="425" alt="flage 3" src="https://github.com/user-attachments/assets/f2d16eda-8dcd-4b52-b4c7-d795f45124ca" />


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
