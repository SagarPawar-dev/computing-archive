# Computing Archive

> You learn security by building, not by consuming. The internet has a basement, grab a flashlight and go look.

Welcome to my cybersecurity and systems engineering archive! This repository documents my hands-on journey from a complete beginner with zero command-line experience to understanding Linux internals, DevOps infrastructure, networking, and offensive security.

---

## 📑 Table of Contents (Quick Index)

* [👤 Profile](#-profile)
* [🗂️ Repository Structure](#️-repository-structure)
* [🗺️ The Learning Roadmap](#️-the-learning-roadmap)
  * [Phase 1: Terminal & Linux Fluency (Current)](#phase-1-terminal--linux-fluency-current)
    * [🎮 OverTheWire: Bandit](#-overthewire-bandit)
    * [🐧 Linux Upskill Challenge](#-linux-upskill-challenge)
    * [🛠️ SadServers](#️-sadservers)
  * [Phase 2: Networking & The Web](#phase-2-networking--the-web)
    * [🦈 Wireshark & Packet Analysis](#-wireshark--packet-analysis)
    * [🕸️ PortSwigger Web Security Academy](#️-portswigger-web-security-academy)
  * [Phase 3: The DevOps Bridge (Containers & Cloud)](#phase-3-the-devops-bridge-containers--cloud)
    * [🐳 Docker & Container Security](#-docker--container-security)
    * [☁️ CloudGoat & Kubernetes Goat](#️-cloudgoat--kubernetes-goat)
* [📜 Golden Rules](#-golden-rules)

---

## 👤 Profile
* **Author:** Sagar Pawar ([@SagarPawar-dev](https://github.com/SagarPawar-dev))
* **Primary OS:** Linux Mint
* **Goal:** Demystify computers, master the Linux terminal, understand modern DevOps/cloud architecture, and learn ethical hacking from the ground up.

---

## 🗂️ Repository Structure

```text
computing-archive/
├── README.md               # Main journey overview, clickable index & progress
├── .gitignore              # Ignored files (passwords, temp files)
├── bandit/                 # OverTheWire: Bandit notes & command breakdowns
│   └── bandit00-to-05.md   # Levels 00 to 05 notes
├── linux/                  # Linux fundamentals & command cheatsheets
└── scripts/                # Custom automation tools & bash scripts
```

---

## 🗺️ The Learning Roadmap

---

### Phase 1: Terminal & Linux Fluency (Current)

#### 🎮 [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/)
* **Official Website:** [overthewire.org/wargames/bandit](https://overthewire.org/wargames/bandit/)
* **Official Docs & Info:** [OverTheWire Wargames Info](https://overthewire.org/information/)
* **My Notes & Writeups:** [`bandit/bandit00-to-05.md`](bandit/bandit00-to-05.md)
* **Description:** A beginner-friendly wargame played directly via SSH in the Linux terminal. It teaches fundamental commands, file navigation, hidden directories, permissions, file analysis, and shell quirks.
* **Progress Tracker:**
  - [x] **Level 00 → 01:** First SSH connection, host key verification, `ls`, reading `readme` with `cat`
  - [x] **Level 01 → 02:** Reading files named with special characters (the dash `-`)
  - [x] **Level 02 → 03:** Reading files with spaces in their name and leading dashes
  - [x] **Level 03 → 04:** Hidden files in directories (`ls -la`), understanding `.` and `..`
  - [x] **Level 04 → 05:** Inspecting file types (`file ./*`), ASCII text vs. binary data
  - [ ] **Level 05 → 06:** Finding files by size and properties (`find`)

#### 🐧 [Linux Upskill Challenge](https://linuxupskillchallenge.com/)
* **Official Website:** [linuxupskillchallenge.com](https://linuxupskillchallenge.com/)
* **Community:** [reddit.com/r/linuxupskillchallenge](https://www.reddit.com/r/linuxupskillchallenge/)
* **Description:** A free, month-long daily challenge that teaches practical Linux server administration on a live remote cloud machine.
* **Status:** Scheduled after Bandit Phase 1.

#### 🛠️ [SadServers](https://sadservers.com/)
* **Official Website:** [sadservers.com](https://sadservers.com/)
* **Description:** "Like LeetCode for Linux & DevOps." Live, broken Linux servers inside your browser where you must debug processes, network issues, and disk faults under operational constraints.
* **Status:** Scheduled.

---

### Phase 2: Networking & The Web

#### 🦈 [Wireshark & Packet Analysis](https://www.wireshark.org/)
* **Official Website:** [wireshark.org](https://www.wireshark.org/)
* **Official Docs:** [Wireshark User's Guide](https://www.wireshark.org/docs/)
* **Description:** The world's foremost network protocol analyzer. Capturing live network packets to inspect the TCP 3-way handshake, DNS queries, and raw HTTP payloads.
* **Status:** Upcoming.

#### 🕸️ [PortSwigger Web Security Academy](https://portswigger.net/web-security)
* **Official Website:** [portswigger.net/web-security](https://portswigger.net/web-security)
* **Official Docs:** [Web Security Documentation](https://portswigger.net/web-security/all-materials)
* **Description:** The premier, 100% free web security training lab built by the creators of Burp Suite. Covers SQL Injection, Cross-Site Scripting (XSS), Authentication vulnerabilities, and IDORs.
* **Status:** Upcoming.

---

### Phase 3: The DevOps Bridge (Containers & Cloud)

#### 🐳 [Docker & Container Security](https://docs.docker.com/)
* **Official Documentation:** [docs.docker.com](https://docs.docker.com/)
* **Cheat Sheet & Security Guide:** [HackTricks Docker Security](https://book.hacktricks.xyz/linux-hardening/privilege-escalation/docker-breakout)
* **Description:** Understanding namespaces, cgroups, container isolation, and how misconfigurations (like mounting `/var/run/docker.sock` or running `--privileged`) lead to host takeover.
* **Status:** Upcoming.

#### ☁️ [CloudGoat & Kubernetes Goat](https://github.com/RhinoSecurityLabs/cloudgoat)
* **CloudGoat (AWS):** [github.com/RhinoSecurityLabs/cloudgoat](https://github.com/RhinoSecurityLabs/cloudgoat)
* **Kubernetes Goat:** [madhuakula.com/kubernetes-goat](https://madhuakula.com/kubernetes-goat/)
* **Description:** Vulnerable-by-design cloud and Kubernetes environments designed to learn cloud misconfigurations, IAM privilege escalation, and cluster hacking.
* **Status:** Upcoming.

---

## 📜 Golden Rules
1. **Never copy-paste blindly:** If a command is used, understand what every flag does.
2. **Build, don't just watch:** Frustration at the terminal is the actual feeling of learning.
3. **Document everything:** Explain *why* a solution works so future-me remembers it.
