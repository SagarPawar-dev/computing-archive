# Computing Archive

> You learn engineering by shipping real things, not by planning to ship them.

An open, hands-on archive documenting a practical journey from beginner to production-grade full-stack engineer with cloud and DevOps capabilities.

Inspired by the philosophy of **The Odin Project**: practical, project-first, zero-fluff, and completely transparent from day one.

---

## 📑 Table of Contents

* [👤 Profile](#-profile)
* [💡 Vision: The Open Curriculum](#-vision-the-open-curriculum)
* [🗂️ Repository Structure](#️-repository-structure)
* [🗺️ The Master Roadmap](#️-the-master-roadmap)
  * [Phase 0: Linux & Systems Foundations (Current)](#phase-0-linux--systems-foundations-current)
  * [Phase 1: Full Stack Web Development (Current Primary)](#phase-1-full-stack-web-development-current-primary)
  * [Phase 2: Networking & How the Web Works](#phase-2-networking--how-the-web-works)
  * [Phase 3: Containers & Deployment (Docker)](#phase-3-containers--deployment-docker)
  * [Phase 4: Cloud Engineering (AWS)](#phase-4-cloud-engineering-aws)
  * [Phase 5: DevOps and Production Automation](#phase-5-devops-and-production-automation)
  * [Phase 6: Capstones & Certifications](#phase-6-capstones--certifications)
* [📜 Golden Rules & Documentation Standard](#-golden-rules--documentation-standard)

---

## 👤 Profile

* **Author:** Sagar Pawar ([@SagarPawar-dev](https://github.com/SagarPawar-dev))
* **Primary OS:** Linux Mint
* **Goal:** Build real full-stack products with JavaScript/TypeScript, understand the infrastructure they run on, and operate them in the cloud like a production engineer.

---

## 💡 Vision: The Open Curriculum

Most cloud and DevOps resources are either expensive certifications or disconnected tutorial fragments. **The Odin Project** proved that the best way to master web development is a structured, markdown-driven, open curriculum with real projects.

This repository is the working laboratory and source documentation for that same vision, applied to full-stack engineering and cloud infrastructure:
1. **Markdown-First Knowledge Base:** Every command, concept, failure, and breakthrough is documented in clean, accessible Markdown.
2. **Future Web Documentation:** As these modules mature, this archive will power a free documentation website (Astro Starlight or VitePress) accessible to anyone starting from scratch.

---

## 🗂️ Repository Structure

```text
computing-archive/
├── README.md               # Master roadmap, project vision & active progress tracker
├── .gitignore              # Ignored files (passwords, temp keys, env files)
├── bandit/                 # OverTheWire: Bandit wargame writeups
│   ├── bandit00-to-05.md   # Levels 00-05 (Completed ✅)
│   └── bandit06-to-10.md   # Levels 06-10 (In Progress)
├── linux/                  # Personal Linux command references & Upskill/SadServers notes
├── networking/             # Protocol notes, curl/dig/nc labs
├── fullstack/              # Odin Project architecture notes & extensions (TS, Tailwind)
├── docker/                 # Dockerfiles, Compose configs, container labs
├── aws/                    # AWS service notes, diagrams, lab exercises
├── cicd/                   # GitHub Actions workflows & pipeline configs
└── scripts/                # Bash & Python automation scripts
```

---

## 🗺️ The Master Roadmap

> **How these phases connect:** You are not learning 6 separate subjects. You are building one skill: shipping and running real software. Each phase solves a problem that the previous phase created.

---

### Phase 0: Linux & Systems Foundations (Current)

**Why this comes first:** Every server your full-stack app runs on is a headless Linux machine. SSH, file permissions, processes, and shell scripting are daily tools for any cloud or DevOps engineer. Building fluency now means these never slow you down later.

#### 🎮 [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/)
* **Why Bandit for a web developer:** You will SSH into cloud servers constantly. You will debug permission errors, search log files, write deployment scripts, and pipe command output. Bandit trains all of this under time pressure.
* **Documentation & Writeups:**
  * [`bandit/bandit00-to-05.md`](bandit/bandit00-to-05.md) *(Levels 00–05 Completed ✅)*
  * [`bandit/bandit06-to-10.md`](bandit/bandit06-to-10.md) *(Levels 06–10 Active)*
* **Key Topics:** SSH, file permissions, streams (`stdin`, `stdout`, `stderr`), pipelines, `grep`, `find`, `sort`, `uniq`, `strings`, `base64`.
* **Progress Checklist:**
  - [x] **Level 00 → 01:** First SSH connection, host key verification, `ls`, `cat`
  - [x] **Level 01 → 02:** Special character filenames, `stdin` vs argument parsing
  - [x] **Level 02 → 03:** Files with spaces and leading dashes
  - [x] **Level 03 → 04:** Hidden files (`ls -la`), directory pointers (`.` and `..`)
  - [x] **Level 04 → 05:** File type identification, magic numbers (`file ./*`)
  - [x] **Level 05 → 06:** Recursive file search by size/properties (`find`)
  - [x] **Level 06 → 07:** Root filesystem search, ownership filters, `stderr` redirection (`2>/dev/null`)
  - [x] **Level 07 → 08:** Pattern search in large files (`grep`)
  - [x] **Level 08 → 09:** Sorting and finding unique lines (`sort | uniq -u`)
  - [x] **Level 09 → 10:** Extracting text from binary files (`strings`)
  - [ ] **Level 10 → 11:** Base64 decoding (`base64 -d`)

#### 🐧 [Linux Upskill Challenge](https://linuxupskillchallenge.com/)
* **Focus:** Daily remote Linux server administration tasks (package management, users, `systemd` services, UFW firewall, cron jobs, log monitoring) on a live cloud VPS. This is exactly what managing a deployed application looks like.
* **Status:** Scheduled after Bandit.

#### 🛠️ [SadServers](https://sadservers.com/)
* **Focus:** Live broken Linux servers you must fix by diagnosing crashed services, full disks, permission errors, and broken network routes under pressure. The closest simulation to real production incidents.
* **Status:** Scheduled.

---

### Phase 1: Full Stack Web Development (Current Primary)

**Goal:** Build and ship complete, production-quality web applications following **The Odin Project** curriculum, extended with modern industry tooling (**Tailwind CSS** and **TypeScript**).

#### 📖 Core Curriculum: [The Odin Project (Full Stack JavaScript)](https://www.theodinproject.com/paths/full-stack-javascript)
* [x] **Foundations Path (Completed ✅):** Web basics, Git/GitHub workflow, HTML, CSS (Flexbox), JavaScript fundamentals, DOM manipulation, problem solving.
* [ ] **Intermediate HTML & CSS (In Progress):** CSS Grid, forms and client-side validation, SVG, CSS variables, positioning.
* [ ] **JavaScript:** OOP, factory functions, ES6 classes and modules, npm & Webpack, asynchronous JS and APIs, testing with Jest, CS fundamentals (recursion, time/space complexity, data structures).
* [ ] **Advanced HTML & CSS:** Animations, responsive design, web accessibility (a11y).
* [ ] **React:** Functional components, hooks (`useState`, `useEffect`), React Router, data fetching, state management, component testing (e.g., Shopping Cart, Memory Card).
* [ ] **NodeJS & Databases:** Node.js, Express, REST APIs, **PostgreSQL**, **Prisma ORM**, authentication (sessions/JWT), backend testing, and full-stack capstones (Blog API, Where's Waldo, Odin-Book).
* [ ] **Getting Hired:** Resume, GitHub portfolio polish, technical interviewing.

#### 🧩 Essential Stack Extensions (Beyond TOP)
Because The Odin Project focuses on core fundamentals and omits utility CSS and static typing, I am adding these two industry-standard layers on top of the path:
* **Tailwind CSS:** Utility-first styling for building clean, responsive React interfaces quickly.
  * Docs: [Tailwind CSS Documentation](https://tailwindcss.com/docs)
* **TypeScript:** Adding static types across React frontends and Node.js/Express backends to catch bugs at compile time and write maintainable production code.
  * Docs & Guides: [TypeScript Handbook](https://www.typescriptlang.org/docs/) and [Total TypeScript Tutorials](https://www.totaltypescript.com/tutorials)

#### ✨ AI Integration (Interview Differentiator)
* Integrate the [Gemini API](https://ai.google.dev/) or [OpenAI API](https://platform.openai.com/docs/) into a full-stack capstone project (e.g., an AI-assisted feature with streaming responses or structured output) and ship it publicly.

#### 🧠 DSA & CS Fundamentals (Side-by-Side for Interviews)
* **Platform:** [LeetCode](https://leetcode.com/) in **C++** (pattern-focused problem solving across Easy and Medium levels).
* **Core Subjects:** DBMS (normalization, indexing, ACID transactions, SQL joins), Operating Systems (processes, threads, memory), Computer Networks (HTTP, TCP, DNS), and Aptitude.

#### 📚 Reference Docs
* 📖 [The Odin Project: Full Stack JavaScript](https://www.theodinproject.com/paths/full-stack-javascript)
* 📖 [MDN Web Docs](https://developer.mozilla.org/)
* 📖 [PostgreSQL Documentation](https://www.postgresql.org/docs/)
* 📖 [Prisma Documentation](https://www.prisma.io/docs)
* 📺 [The Primeagen](https://www.youtube.com/@ThePrimeagen) (Engineering perspective and systems thinking)

* **Milestone:** Complete the Full Stack JavaScript path and deploy full-stack TypeScript/Tailwind/PostgreSQL projects publicly with clean architecture READMEs.

---

### Phase 2: Networking & How the Web Works

**Why this comes before Docker and Cloud:** When your deployed app breaks, the question is almost always a networking question: "Why can't the client reach the server?", "Why is DNS not resolving?", "Why is the HTTPS certificate failing?" Understanding protocols is what separates engineers who can debug production from those who guess and restart services.

* **What you need to understand concretely:**
  * What actually happens when a browser types `yourapp.com` and hits Enter (DNS -> TCP -> TLS -> HTTP).
  * How HTTP request/response works at the byte level (methods, headers, status codes, body).
  * What a port is, what a socket is, and why your Node.js app binds to port 3000.
  * What HTTPS actually protects and what it does not protect.
  * How a load balancer, reverse proxy (Nginx), and CDN each work.
* **CLI Tools to master:**
  * `curl -v`: Raw HTTP/HTTPS request inspection (headers, TLS handshake, redirects).
  * `dig` / `nslookup`: DNS record lookup and understanding resolution chains.
  * `nc` (Netcat): Raw TCP connections, testing if a port is open.
  * `ss -tuln`: Seeing which ports your running apps are actually listening on.
* **Learning Resources:**
  * 🌐 [How DNS Works](https://howdns.works/) and [Mess with DNS](https://messwithdns.com/) by Julia Evans (interactive, no domain needed)
  * 📺 [Hussein Nasser on YouTube](https://www.youtube.com/@hnasr) (The best resource for HTTP, TCP, proxies, and backend networking)
  * 📺 [Computer Networking Lectures by Jim Kurose](https://www.youtube.com/@JimKurose) (Textbook author's own lectures, free on YouTube)
  * 🕸️ [PortSwigger Web Security Academy](https://portswigger.net/web-security) (Free web security labs, directly relevant to building secure full-stack apps)
* **Milestone:** You can fully explain what happens, at every layer, from the moment a user opens your deployed app's URL to the moment the page loads.

---

### Phase 3: Containers & Deployment (Docker)

**Why Docker:** Your full-stack app works perfectly on your laptop. The moment you try to run it on any other machine (a friend's computer, a CI/CD runner, a cloud VM), it breaks because of different Node.js versions, missing packages, or OS differences. Docker solves this permanently.

> **This phase begins the moment you have a working full-stack project to containerize.** Do not study Docker in isolation before you have a real app to put in it.

* **The Container Learning Ladder:**
  * **Step 1:** Write a `Dockerfile` for your Node.js backend. Build an image. Run a container. Understand layers and caching.
  * **Step 2:** Write a `Dockerfile` for your React frontend. Serve it via Nginx inside a container.
  * **Step 3:** Write a `docker-compose.yml` that runs your full stack together: frontend container + backend container + PostgreSQL container. One command, everything starts.
  * **Step 4:** Debug networking between containers (how does the backend container talk to the database container?).
  * **Step 5:** Add environment variables, volumes, and health checks. Deploy the composed stack to a cloud VM.

  > **Gate:** Only move to Kubernetes after you have shipped a real Docker Compose stack to production and debugged it under real traffic.

* **Learning Resources:**
  * 📺 [Containers from Scratch by Liz Rice (GOTO 2018)](https://www.youtube.com/watch?v=8fi7uSYlOdc) (Understand what a container actually IS at the kernel level)
  * 📺 [Ultimate Docker Compose Tutorial by TechWorld with Nana](https://www.youtube.com/watch?v=SXwC9fSwct8) (Hands-on multi-service stacks)
  * 📖 [Official Docker Documentation](https://docs.docker.com/)
* **Milestone:** Your full-stack app (frontend + backend + database) runs in Docker Compose locally and is deployed to a cloud VM with a single `docker compose up` command.

---

### Phase 4: Cloud Engineering (AWS)

**Why AWS:** AWS has the largest market share globally and in India. Understanding AWS is a prerequisite for most DevOps, platform, and senior backend roles. It is also the platform where your deployed full-stack apps will live at production scale.

> **Learn AWS by deploying your existing projects to it, not by studying services in isolation.**

* **Foundational Services (Learn by doing):**
  * **EC2:** Virtual machines. SSH into them. Install your app. Configure security groups (firewall rules).
  * **S3:** Object storage. Host your React build as a static site. Store uploaded images from your app.
  * **RDS:** Managed PostgreSQL. Move your local database to a managed cloud database.
  * **IAM:** Identity and permissions. Understand why you never use the root account for anything.
  * **Route 53:** DNS for your domain. Point `yourapp.com` to your EC2 instance.
  * **CloudFront:** CDN. Put it in front of your S3 static site for global performance.
  * **VPC:** Networking. Understand public subnets, private subnets, and security groups.
* **Free Learning Path:**
  * 📺 [AWS Free Tier](https://aws.amazon.com/free/) (12 months of free EC2, S3, RDS; build everything here)
  * 📺 [FreeCodeCamp AWS Certified Solutions Architect Course](https://www.youtube.com/watch?v=Ia-UEYYR44s) (Free 10-hour full course on YouTube)
  * 📖 [AWS Documentation](https://docs.aws.amazon.com/)
  * 🏗️ [Cloud Resume Challenge](https://cloudresumechallenge.dev/docs/the-challenge/aws/) (Build a full project using 10+ AWS services. One of the best AWS portfolio projects available.)
* **Target Certification:** AWS Certified Solutions Architect - Associate (SAA-C03). Widely recognized across Indian IT and product companies.
* **Milestone:** Your full-stack app is running on AWS: React on S3 + CloudFront, Node.js on EC2, PostgreSQL on RDS, custom domain on Route 53, with proper IAM roles and security groups.

---

### Phase 5: DevOps and Production Automation

**Why this comes after Cloud:** DevOps makes no sense until you have felt the pain of manually deploying to a cloud server repeatedly. Once you have done `ssh into EC2 -> git pull -> npm install -> restart pm2` ten times, you will understand exactly why CI/CD exists.

* **CI/CD Pipelines:**
  * GitHub Actions: Automated test runs, Docker image builds, and deployments triggered on every `git push`.
  * Goal: Push code to `main` branch -> tests run automatically -> Docker image builds -> deploys to your AWS server. Zero manual steps.
* **Infrastructure as Code (IaC):**
  * Terraform: Define your entire AWS infrastructure (EC2, RDS, S3, VPC, security groups) in code files. Destroy and recreate it in minutes. No clicking in the AWS console.
* **Monitoring & Observability:**
  * What is your app doing right now? Is it healthy? When did it last fail?
  * Tools: AWS CloudWatch (native logs and alerts), Grafana + Prometheus (metrics dashboards).
  * Skill: Reading logs to diagnose a production crash (the single most important operational skill).
* **Kubernetes (Only when needed):**
  * When you have multiple microservices, Kubernetes orchestrates them across multiple machines.
  * Not needed for a single full-stack application. Only enter this territory when the complexity of your system actually requires it.
* **Learning Resources:**
  * 📺 [GitHub Actions Full Course by TechWorld with Nana](https://www.youtube.com/watch?v=R8_veQiYBjI) (Best CI/CD starting point)
  * 📺 [Terraform for Beginners by TechWorld with Nana](https://www.youtube.com/watch?v=l5k1ai_GBDE) (IaC from zero)
  * 📺 [TechWorld with Nana YouTube Channel](https://www.youtube.com/@TechWorldwithNana) (Top free DevOps education channel)
* **Milestone:** A fully automated pipeline where `git push` triggers tests, builds a Docker image, and deploys to AWS with zero manual steps. Infrastructure defined entirely in Terraform code.

---

### Phase 6: Capstones & Certifications

Translating technical capability into portfolio evidence and industry-recognized credentials.

* **Portfolio Projects (What actually gets you hired at product companies):**
  * Full-stack app (TypeScript + React + Node.js + PostgreSQL + Tailwind) with an AI integration, containerized, deployed to AWS with CI/CD and monitoring.
  * Cloud Resume Challenge (AWS): a recognized, public portfolio project that engineering managers respect.
  * Open-source contribution: even a documentation fix or bug fix demonstrates real codebase reading ability.
* **Certifications (Useful for Indian market):**
  * **AWS Certified Solutions Architect - Associate (SAA-C03):** High ROI. Recognized everywhere.
  * **Certified Kubernetes Administrator (CKA):** For when K8s becomes relevant to your work.
  * **DSA Platforms:** 150-200 LeetCode problems (Easy + Medium) solved in C++ for SDE interviews.
* **Job Targets in Indian Market:**
  * **Full Stack + Cloud/DevOps at product companies:** Razorpay, Zerodha, Groww, Meesho, PhonePe, CRED, Juspay, Urban Company, Ola, Swiggy.
  * **Cloud/DevOps at service companies:** TCS Digital, Infosys, Wipro, Cognizant, HCL (AWS certification boosts packages and shortlisting here).

---

## 📜 Golden Rules & Documentation Standard

1. **Ship before you study:** A deployed broken project teaches more than a finished tutorial.
2. **Build, don't watch:** Every hour of video without a corresponding terminal session is wasted.
3. **Write the "Why" before the "How":** Every writeup in this archive follows this structure:
   * **Problem:** What was the actual issue or challenge?
   * **Mental Model:** What system concept (HTTP, file descriptors, DNS, containers) makes this solvable?
   * **Dead Ends:** What was tried first that failed and why?
   * **Solution:** Exact commands or code with line-by-line explanation.
   * **Takeaway:** What production or interview scenario does this connect to?
4. **One working thing beats ten planned things:** The roadmap is a compass, not a contract. The projects you actually ship determine your skill level, not the phases you plan to complete.
