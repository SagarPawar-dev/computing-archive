# Computing Archive

> You learn security by building, not by consuming. The internet has a basement; grab a flashlight and go look.

An open, hands-on archive and learning roadmap covering Linux fundamentals, systems engineering, computer networking, modern DevOps, and ethical hacking. 

Inspired by the philosophy of **The Odin Project**: practical, project-first, zero-fluff, and completely transparent from day one.

---

## 📑 Table of Contents

* [👤 Profile](#-profile)
* [💡 Vision: The Open Curriculum](#-vision-the-open-curriculum)
* [🗂️ Repository Structure](#️-repository-structure)
* [🗺️ The Master Roadmap](#️-the-master-roadmap)
  * [Phase 0: Foundations & Terminal Mastery (Current)](#phase-0-foundations--terminal-mastery-current)
    * [🎮 OverTheWire: Bandit](#-overthewire-bandit)
    * [🐧 Linux Upskill Challenge](#-linux-upskill-challenge)
    * [🛠️ SadServers](#️-sadservers)
  * [Phase 1: Networking & Web Architecture](#phase-1-networking--web-architecture)
  * [Phase 2: Scripting & Tool Building](#phase-2-scripting--tool-building)
  * [Phase 3: Core DevOps & Infrastructure as Code](#phase-3-core-devops--infrastructure-as-code)
  * [Phase 4: Offensive Security & Penetration Testing](#phase-4-offensive-security--penetration-testing)
  * [Phase 5: DevSecOps & Cloud Security](#phase-5-devsecops--cloud-security)
  * [Phase 6: Real-World Capstones & Certifications](#phase-6-real-world-capstones--certifications)
* [📜 Golden Rules](#-golden-rules)

---

## 👤 Profile

* **Author:** Sagar Pawar ([@SagarPawar-dev](https://github.com/SagarPawar-dev))
* **Primary OS:** Linux Mint
* **Goal:** Demystify computing from the hardware and kernel up to the cloud, bridge software engineering with offensive security, and document everything publicly.

---

## 💡 Vision: The Open Curriculum

Most cybersecurity and DevOps resources are either paywalled certifications or disconnected video tutorials. **The Odin Project** proved that the best way to master web development is a structured, markdown-driven, open curriculum with real projects.

This repository serves as the working laboratory and source documentation for that exact vision:
1. **Markdown-First Knowledge Base:** Every command, concept, failure, and breakthrough is documented in clean, accessible Markdown.
2. **Future Web Documentation:** As these modules mature, this archive will power a dedicated documentation website (built with modern static documentation engines like Astro Starlight or VitePress) freely accessible to anyone starting from scratch.

---

## 🗂️ Repository Structure

```text
computing-archive/
├── README.md               # Master roadmap, project vision & active tracker
├── .gitignore              # Ignored files (passwords, temporary keys, env files)
├── bandit/                 # OverTheWire: Bandit challenge writeups & command breakdowns
│   ├── bandit00-to-05.md   # Levels 00 to 05 writeups (Completed ✅)
│   └── bandit06-to-10.md   # Levels 06 to 10 writeups (In Progress)
├── networking/             # Packet captures, protocol notes & Wireshark labs
├── scripting/              # Custom Bash tools & Python security scripts
├── devops/                 # Dockerfiles, CI/CD pipelines & Terraform templates
└── web-security/           # PortSwigger notes, vulnerability writeups & PoCs
```

---

## 🗺️ The Master Roadmap

---

### Phase 0: Foundations & Terminal Mastery (Current)

The bedrock. Developing complete fluency in headless Linux systems, shell navigation, standard streams, file analysis, and debugging broken servers.

#### 🎮 [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/)
* **Official Website:** [overthewire.org/wargames/bandit](https://overthewire.org/wargames/bandit/)
* **Documentation & Writeups:**
  * [`bandit/bandit00-to-05.md`](bandit/bandit00-to-05.md) *(Levels 00–05 Completed ✅)*
  * [`bandit/bandit06-to-10.md`](bandit/bandit06-to-10.md) *(Levels 06–10 Active)*
* **Key Topics:** SSH authentication, handling obscure filenames, hidden directories, file type identification, recursive search (`find`), standard streams redirection (`stdin`, `stdout`, `stderr`), pipelines, text processing (`grep`, `sort`, `uniq`, `strings`, `base64`).
* **Progress Checklist:**
  - [x] **Level 00 → 01:** First SSH connection, host key verification, `ls`, `cat readme`
  - [x] **Level 01 → 02:** Standard input vs dash filename, option delimiter (`cat ./-` or `cat -- -`)
  - [x] **Level 02 → 03:** Handling file spaces and leading dashes (`cat -- "--spaces..."`)
  - [x] **Level 03 → 04:** Hidden files in directories (`ls -la`), directory pointers (`.` and `..`)
  - [x] **Level 04 → 05:** Extension-agnostic file types, magic numbers, ASCII vs binary (`file ./*`)
  - [x] **Level 05 → 06:** Finding files by size and properties (`find . -type f -size 1033c ! -executable`)
  - [ ] **Level 06 → 07:** Root searches (`find /`), ownership filters (`-user`, `-group`), stderr redirection (`2>/dev/null`)
  - [ ] **Level 07 → 08:** Pattern searching in large datasets (`grep`)
  - [ ] **Level 08 → 09:** Sorting streams and finding unique lines (`sort | uniq -u`)
  - [ ] **Level 09 → 10:** Extracting human-readable text from binary garbage (`strings`)
  - [ ] **Level 10 → 11:** Base64 decoding (`base64 -d`)

#### 🐧 [Linux Upskill Challenge](https://linuxupskillchallenge.com/)
* **Official Website:** [linuxupskillchallenge.com](https://linuxupskillchallenge.com/)
* **Focus:** Practical remote Linux server administration. Spin up an independent cloud machine (AWS/Azure/DigitalOcean) and complete daily sysadmin tasks: package management, user management, firewall rules (UFW), system services (`systemd`), and log monitoring.
* **Status:** Scheduled following Bandit.

#### 🛠️ [SadServers](https://sadservers.com/)
* **Official Website:** [sadservers.com](https://sadservers.com/)
* **Focus:** Hands-on Linux troubleshooting. Live, broken servers where you are dropped into a terminal and must diagnose crashed services, exhausted disk space, permission deadlocks, and broken network routes.
* **Status:** Scheduled.

---

### Phase 1: Networking & Web Architecture

Understanding how computers talk to each other across cables, airwaves, and the global internet.

* **Core Theory:**
  * OSI & TCP/IP models, packet encapsulation, MAC vs IP addressing, Subnetting (CIDR).
  * Protocols: ARP, ICMP, TCP (3-way handshake, flags, teardown), UDP, DNS, DHCP.
  * Web protocols: HTTP/1.1 vs HTTP/2, TLS/SSL handshake, certificate validation, WebSockets, REST APIs.
* **Practical Labs:**
  * **[Wireshark](https://www.wireshark.org/):** Live packet capture and traffic dissection (TCP streams, DNS queries, unencrypted payloads).
  * **[PortSwigger Web Security Academy](https://portswigger.net/web-security):** The gold standard of web security training. Hands-on labs covering SQL Injection, Cross-Site Scripting (XSS), Cross-Site Request Forgery (CSRF), Insecure Direct Object References (IDOR), and Server-Side Request Forgery (SSRF).
* **Milestone:** Ability to intercept, dissect, and manipulate arbitrary network and web traffic between client and server.

---

### Phase 2: Scripting & Tool Building

Moving from running other people's tools to writing custom automation and security software.

* **Bash Automation:**
  * Shell scripting fundamentals, control flow, functions, positional parameters.
  * Text processing powerhouses: `sed`, `awk`, regex (`grep -E`), cron automation.
* **Python for Hackers & DevOps:**
  * Raw network sockets, building custom port scanners and banner grabbers.
  * Writing custom exploit scripts, fuzzers, and HTTP request automation (`requests` library).
  * Interacting with APIs and parsing JSON/YAML payloads.
* **Git Mastery:**
  * Branching strategies, interactive rebasing, merge conflict resolution, Git hooks, internal architecture (`.git/objects`).
* **Milestone:** Ability to build a functioning reconnaissance scanner or server monitoring script from scratch without third-party frameworks.

---

### Phase 3: Core DevOps & Infrastructure as Code

Understanding how modern software is built, packaged, shipped, and scaled automatically.

* **Containers & Virtualization:**
  * Docker: Images, layers, Dockerfiles, multi-stage builds, networking, volumes, Compose.
  * Linux container internals: Namespaces (`pid`, `net`, `mnt`), cgroups, rootless execution.
* **CI/CD Pipelines:**
  * GitHub Actions / GitLab CI: Automated testing, code linting, security checks, automated deployments.
* **Infrastructure as Code (IaC):**
  * Terraform: Declarative cloud provisioning, state files, modules, multi-environment setups.
* **Orchestration:**
  * Kubernetes: Architecture (Control Plane, Kubelet, etcd), Pods, Deployments, Services, ConfigMaps, Ingress controllers.
* **Observability:**
  * Metrics, logs, and traces: Prometheus, Grafana, Linux systemd journal logs.
* **Milestone:** Write application code, push to Git, and have it automatically tested, containerized, and deployed to cloud infrastructure with zero manual intervention.

---

### Phase 4: Offensive Security & Penetration Testing

Learning the attacker methodology to identify vulnerabilities before malicious actors do.

* **Reconnaissance & Enumeration:**
  * Host discovery, port scanning (`nmap`, `masscan`), service fingerprinting, web directory fuzzing (`ffuf`, `gobuster`).
* **Exploitation:**
  * Vulnerability research, searchsploit, modifying public exploit PoCs, reverse shells vs bind shells.
* **Privilege Escalation:**
  * Linux: SUID/SGID binaries, misconfigured sudo rules, readable shadow files, cron job hijacking, kernel exploits.
  * Windows: Service misconfigurations, unquoted service paths, token manipulation.
* **Enterprise Networks & Active Directory:**
  * Kerberos authentication, Kerberoasting, AS-REP roasting, BloodHound domain mapping, Pass-the-Hash.
* **Platforms:**
  * [TryHackMe](https://tryhackme.com/) (Pre-Security → Complete Beginner → Jr Penetration Tester)
  * [HackTheBox](https://www.hackthebox.com/) (Starting Point → Easy/Medium Linux & Windows Machines)
* **Milestone:** Ability to conduct a structured penetration test against a network, compromise endpoints, and escalate to root/Domain Admin.

---

### Phase 5: DevSecOps & Cloud Security

Where development, operations, and security converge: securing cloud architecture and the software supply chain.

* **Cloud Security (AWS / GCP):**
  * Identity & Access Management (IAM) least privilege, role assumption, S3 security policies, VPC networking, security groups.
  * [CloudGoat](https://github.com/RhinoSecurityLabs/cloudgoat): Vulnerable-by-design AWS environments for testing IAM escalation and cloud lateral movement.
* **Container & Cluster Security:**
  * [Kubernetes Goat](https://madhuakula.com/kubernetes-goat/): Exploiting misconfigured Kubernetes clusters.
  * Image scanning: Trivy, Grype for CVE scanning in container layers.
  * Runtime security: Falco, AppArmor, Seccomp profiles.
* **Pipeline Security (Shift Left):**
  * SAST (Static Application Security Testing): Semgrep, SonarQube.
  * DAST (Dynamic Application Security Testing): OWASP ZAP in CI/CD.
  * Secrets detection: Gitleaks, TruffleHog.
  * Software Bill of Materials (SBOM) and supply chain protection.
* **Milestone:** Designing a hardened cloud delivery pipeline that automatically halts deployments when insecure code, unpatched base images, or leaked secrets are detected.

---

### Phase 6: Real-World Capstones & Certifications

Translating technical capability into industry-recognized achievements and production-grade work.

* **Offensive Track Capstones:**
  * Active participation in Bug Bounty programs (HackerOne, Bugcrowd).
  * Certifications: CompTIA Security+ (baseline) → PNPT / OSCP (Offensive Security Certified Professional).
* **DevOps / Cloud Track Capstones:**
  * Production-grade infrastructure portfolio: Terraform-managed Kubernetes cluster hosting a microservices app with automated CI/CD and observability.
  * Certifications: Certified Kubernetes Administrator (CKA), AWS Certified Solutions Architect / AWS Certified Security - Specialty.
* **Open Source Contribution:**
  * Contributing code, documentation, or tooling to open-source security or DevOps utilities.

---

## 📜 Golden Rules

1. **Never copy-paste blindly:** If a command is used, know what every flag and pipe does before hitting Enter.
2. **Build, don't just watch:** Reading or watching videos is passive; running into terminal errors and solving them is where real learning happens.
3. **Document everything:** Explain why a solution works so future-you and fellow engineers can learn from it.
4. **Security through understanding:** Attackers and defenders use the exact same operating system primitives. Learn how things work normally, and how they break becomes obvious.
