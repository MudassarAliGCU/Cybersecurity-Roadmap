# 🌐 Networking

> **Section 02 of the Cybersecurity Roadmap**
> Building the foundation every hacker, defender, and engineer stands on.

---

## 📖 Introduction

**Networking is the invisible language that lets machines talk to each other.** Every email sent, every website loaded, every packet captured, and every attack launched or blocked travels across a network. Without understanding how data moves — from the electrical signals on a cable to the routing decisions made across continents — you cannot truly understand computers, and you certainly cannot secure them.

### 🔑 Why Networking Is the Backbone of Cybersecurity

Cybersecurity is, at its core, the practice of protecting **systems that communicate**. Firewalls, intrusion detection systems, VPNs, malware command-and-control channels, phishing infrastructure, and even physical security systems all rely on networking concepts. You cannot defend what you don't understand, and you cannot attack — ethically or otherwise — what you cannot map.

### 🎯 Why Every Ethical Hacker and Defender Must Master This

- **Penetration testers** need networking to scan, enumerate, pivot, and exploit systems across segmented environments.
- **SOC analysts** need networking to read packet captures, interpret firewall logs, and detect anomalies in traffic flow.
- **System administrators** need networking to design secure, resilient infrastructure.
- **Incident responders** need networking to trace lateral movement and contain breaches.

Networking isn't a "nice to have" skill in cybersecurity — it is the **prerequisite language** the entire field is written in.

### 📦 What This Section Covers

This section takes you from **zero knowledge** to a **confident, practical understanding** of networking — covering models, devices, media, addressing, protocols, ports, routing, services, security, monitoring, scanning, wireless, and cloud networking. Every topic is paired with **hands-on labs** so you learn by doing, not just reading.

---

## 🎯 Learning Objectives

By the end of this section, you will be able to:

- ✅ Explain how data travels across a network using the OSI and TCP/IP models
- ✅ Identify and describe the function of core network devices (routers, switches, firewalls, etc.)
- ✅ Differentiate between types of network media (copper, fiber, wireless)
- ✅ Understand and calculate IPv4/IPv6 addressing and subnetting
- ✅ Explain core networking protocols (TCP, UDP, DNS, DHCP, HTTP/S, ARP, ICMP, etc.)
- ✅ Identify common ports and the services running on them
- ✅ Understand routing and switching fundamentals
- ✅ Configure and troubleshoot basic network services
- ✅ Apply foundational network security principles (firewalls, VLANs, segmentation)
- ✅ Use monitoring tools to analyze live network traffic
- ✅ Perform basic and intermediate network scanning with Nmap
- ✅ Understand wireless networking standards and vulnerabilities
- ✅ Understand cloud networking fundamentals (VPCs, subnets, security groups)
- ✅ Build a functioning home lab for continuous practice
- ✅ Prepare confidently for Network+, CCNA, Security+, and offensive security certifications

---

## 📋 Prerequisites

Before starting this section, make sure you've completed:

| Chapter | Status |
|---------|--------|
| 🖥️ **00 – Computer Hardware** | Required |
| 💻 **01 – Operating Systems** | Required |
| ⌨️ **Basic Computer Skills** | Required |

> 💡 If you haven't completed these, go back and finish them first — networking concepts build directly on hardware and OS fundamentals.

---

## 🗺️ Learning Path

```
            🚀 Introduction
                  ↓
          🧩 Network Models
                  ↓
          🖧 Network Devices
                  ↓
          🔌 Network Media
                  ↓
          🔢 IP Addressing
                  ↓
          📡 Protocols
                  ↓
          🚪 Ports
                  ↓
     🔀 Routing & Switching
                  ↓
        🛠️ Network Services
                  ↓
        🛡️ Network Security
                  ↓
          📊 Monitoring
                  ↓
          🔍 Scanning
                  ↓
      📶 Wireless Networking
                  ↓
        ☁️ Cloud Networking
                  ↓
              🧪 Labs
                  ↓
           🚧 Projects
                  ↓
   🎓 Certification Preparation
```

---
# 🗺️ Learning Roadmap

> Follow the chapters in the order below. Each chapter builds upon the previous one, combining theory, practical labs, projects, and real-world cybersecurity applications. By the end of this section, you'll have a solid networking foundation for cybersecurity, system administration, and penetration testing.

| No. | Chapter | Difficulty | Est. Time | What You'll Learn |
|:---:|:--------|:----------:|:---------:|:------------------|
| **00** | **📖 [Introduction](00-Introduction/README.md)** | 🟢 Beginner | **2–3 hrs** | Discover what computer networking is, why it is fundamental to cybersecurity, explore different network types, client-server and peer-to-peer architectures, and common network topologies. |
| **01** | **🧩 [Network Models](01-Network%20Models/README.md)** | 🟢 Beginner | **4–6 hrs** | Learn the OSI and TCP/IP models, understand encapsulation and decapsulation, and see how data travels through every layer of a network. |
| **02** | **🖧 [Network Devices](02-Network%20Devices/README.md)** | 🟢 Beginner | **6–8 hrs** | Understand the purpose and operation of routers, switches, hubs, bridges, gateways, firewalls, wireless access points, IDS/IPS, and load balancers. |
| **03** | **🔌 [Network Media](03-Network%20Media/README.md)** | 🟢 Beginner | **3–5 hrs** | Study copper cables, fiber optics, coaxial cables, Ethernet standards, wireless communication technologies, and physical network connectivity. |
| **04** | **🌍 [IP Addressing](04-IP%20Addressing/README.md)** | 🟡 Beginner → Intermediate | **10–15 hrs** | Master IPv4, IPv6, subnetting, CIDR notation, VLSM, public and private addressing, APIPA, loopback addresses, and IP planning. |
| **05** | **📡 [Network Protocols](05-Network%20Protocols/README.md)** | 🟡 Intermediate | **12–18 hrs** | Learn how essential protocols such as TCP, UDP, ARP, ICMP, DNS, DHCP, HTTP, HTTPS, SSH, FTP, SMTP, LDAP, SMB, Kerberos, and others enable communication across networks. |
| **06** | **🚪 [Ports & Services](06-Ports/README.md)** | 🟢 Beginner | **3–5 hrs** | Understand TCP and UDP ports, service mappings, well-known ports, ephemeral ports, and why ports play a crucial role in system administration and cybersecurity. |
| **07** | **🔀 [Routing & Switching](07-Routing%20and%20Switching/README.md)** | 🟡 Intermediate | **12–16 hrs** | Explore routing concepts, switching operations, VLANs, trunking, STP, NAT, PAT, and dynamic routing protocols such as RIP, OSPF, and BGP. |
| **08** | **🛠️ [Network Services](08-Network%20Services/README.md)** | 🟡 Intermediate | **6–8 hrs** | Learn how enterprise services such as DNS, DHCP, VPNs, web servers, proxy servers, file servers, mail servers, and reverse proxies support modern networks. |
| **09** | **🛡️ [Network Security](09-Network%20Security/README.md)** | 🟡 Intermediate | **10–14 hrs** | Understand firewall technologies, ACLs, VPNs, IDS/IPS, network segmentation, Zero Trust principles, secure network architecture, and common network attacks. |
| **10** | **📊 [Network Monitoring](10-Network%20Monitoring/README.md)** | 🟡 Intermediate | **8–12 hrs** | Analyze network traffic using Wireshark and tcpdump, understand packet captures, log analysis, monitoring strategies, and SIEM fundamentals. |
| **11** | **🔍 [Network Scanning](11-Network%20Scanning/README.md)** | 🟡 Intermediate | **8–12 hrs** | Perform host discovery, service enumeration, banner grabbing, vulnerability scanning, and network reconnaissance using tools such as Nmap and Masscan. |
| **12** | **📶 [Wireless Networking](12-Wireless%20Networking/README.md)** | 🟡 Intermediate | **6–8 hrs** | Learn wireless communication, IEEE 802.11 standards, Wi-Fi security protocols, wireless attacks, rogue access points, Evil Twin attacks, and wireless defense techniques. |
| **13** | **☁️ [Cloud Networking](13-Cloud%20Networking/README.md)** | 🟡 Intermediate | **8–12 hrs** | Understand virtual networking in cloud environments including VPCs, Security Groups, Network ACLs, VPN Gateways, Load Balancers, and hybrid cloud connectivity. |
| **14** | **🧪 [Hands-on Labs](14-Labs/README.md)** | 🔵 Practical | **25+ hrs** | Reinforce every networking concept through guided Packet Tracer labs, Wireshark exercises, Nmap practice, TryHackMe rooms, Hack The Box challenges, and home lab projects. |
| **15** | **⚡ [Cheat Sheets](15-Cheat%20Sheets/README.md)** | 📚 Reference | **As Needed** | Quickly review networking commands, protocols, port numbers, subnetting shortcuts, Wireshark filters, and essential networking concepts during study or revision. |
| **16** | **📖 [Glossary](16-Glossary/README.md)** | 📚 Reference | **As Needed** | Review networking terminology, acronyms, protocol definitions, and important concepts explained throughout the networking curriculum. |
| **17** | **📚 [Resources](17-Resources/README.md)** | 📚 Reference | **Continuous** | Access carefully selected books, official documentation, RFCs, YouTube channels, courses, websites, practice platforms, and certification resources. |
| **18** | **📝 [Blogs & Learning Journal](18-Blogs/README.md)** | 🟢 Beginner | **Weekly** | Document your learning journey, publish technical write-ups, summarize labs, reflect on challenges, and build a professional cybersecurity portfolio. |
| **19** | **🚀 [Projects](19-Projects/README.md)** | 🔴 Advanced Practice | **20+ hrs** | Apply your knowledge by designing networks, performing security assessments, analyzing packet captures, auditing infrastructures, and completing portfolio-worthy projects. |
| **20** | **🎓 [Certification Notes](20-Certification%20Notes/README.md)** | 🏆 Career | **Continuous** | Organize exam objectives, revision notes, commands, labs, study guides, and preparation material for Network+, CCNA, Security+, eJPT, PNPT, and OSCP. |

---

## 🎯 Completion Goal

By completing every chapter in this Networking section, you will:

- ✅ Understand how modern computer networks operate from the physical layer to cloud environments.
- ✅ Build practical experience using industry-standard networking and security tools.
- ✅ Develop the troubleshooting skills required to analyze, diagnose, and secure networks.
- ✅ Gain a strong foundation for penetration testing, SOC operations, system administration, and cloud security.
- ✅ Be well prepared to continue with the **Linux** section and pursue certifications such as **CompTIA Network+**, **CCNA**, **Security+**, and **eJPT**.

---

## 🧪 Hands-on Labs

Theory alone won't make you network-literate — **you must practice**. This section integrates the following tools throughout:

- 🖧 **Cisco Packet Tracer** — Simulate routers, switches, and topologies to practice CCNA-style configurations without physical hardware.
- 🦈 **Wireshark** — Capture and analyze live network traffic to understand protocols at the packet level.
- 🔍 **Nmap** — Scan networks, discover hosts, and enumerate open ports and services.
- 📟 **TCPDump** — Perform lightweight, command-line packet capturing on Linux systems.
- 🚩 **TryHackMe** — Complete guided, beginner-friendly networking rooms.
- 📦 **Hack The Box** — Apply networking knowledge in realistic penetration testing scenarios.
- 🏠 **Home Lab** — Build a personal lab using VirtualBox/VMware, pfSense, and virtual switches to practice safely and repeatedly.

---

## 🛠️ Tools Covered

| Tool | Purpose |
|------|---------|
| **Cisco Packet Tracer** | Network simulation and CCNA-style configuration practice |
| **Wireshark** | Deep packet inspection and protocol analysis |
| **Nmap** | Network scanning, host discovery, port enumeration |
| **TCPDump** | Command-line packet capture on Linux/Unix systems |
| **Netcat (nc)** | Banner grabbing, port testing, simple connections |
| **Ping / Traceroute** | Basic connectivity and path troubleshooting |
| **ipconfig / ifconfig / ip** | Viewing and configuring network interfaces |
| **Netstat / ss** | Viewing active connections and listening ports |
| **pfSense** | Firewall and router simulation for home labs |
| **GNS3** | Advanced network emulation for complex topologies |

---

## 🎓 Certifications Supported

This section is designed to build a strong foundation for the following industry certifications:

### 🅰️ CompTIA Network+
Covers foundational networking knowledge directly aligned with the Network+ exam objectives — models, devices, media, addressing, protocols, and troubleshooting.

### 🅱️ CCNA (Cisco Certified Network Associate)
Provides the routing, switching, and Packet Tracer practice needed to begin serious CCNA exam preparation.

### 🅲️ CompTIA Security+
Builds the networking security fundamentals (firewalls, VLANs, segmentation) required before tackling Security+ security concepts.

### 🅳️ eJPT (eLearnSecurity Junior Penetration Tester)
Strengthens the scanning, enumeration, and protocol analysis skills tested in eJPT's practical exam.

### 🅴️ PNPT (Practical Network Penetration Tester)
Prepares you for real-world network pivoting, enumeration, and exploitation scenarios central to the PNPT certification.

### 🅵️ OSCP (Offensive Security Certified Professional)
Establishes the deep networking fluency required to understand exploitation paths, pivoting, and traffic analysis in the OSCP labs and exam.

---

## 📖 Learning Resources

### 📘 Official Documentation
- [Cisco Networking Academy](https://www.netacad.com/)
- [Microsoft Learn – Networking](https://learn.microsoft.com/en-us/training/browse/?terms=networking)
- [Cloudflare Learning Center](https://www.cloudflare.com/learning/)
- [RFC Editor](https://www.rfc-editor.org/)
- [Wireshark Documentation](https://www.wireshark.org/docs/)
- [Nmap Documentation](https://nmap.org/book/man.html)

### 🎥 YouTube Channels & Instructors
- [Professor Messer](https://www.professormesser.com/)
- [Jeremy's IT Lab](https://www.youtube.com/@JeremysITLab)
- [NetworkChuck](https://www.youtube.com/@NetworkChuck)
- [David Bombal](https://www.youtube.com/@davidbombal)
- [John Hammond](https://www.youtube.com/@_JohnHammond)

### 🏋️ Practice Platforms
- [TryHackMe](https://tryhackme.com/)
- [Hack The Box](https://www.hackthebox.com/)
- [OverTheWire](https://overthewire.org/wargames/)
- [Cisco Skills for All](https://skillsforall.com/)

---

## 🗂️ Repository Structure

```
02-Networking/
├── README.md
├── 00-Introduction/
├── 01-Network Models/
├── 02-Network Devices/
├── 03-Network Media/
├── 04-IP Addressing/
├── 05-Network Protocols/
├── 06-Ports/
├── 07-Routing and Switching/
├── 08-Network Services/
├── 09-Network Security/
├── 10-Network Monitoring/
├── 11-Network Scanning/
├── 12-Wireless Networking/
├── 13-Cloud Networking/
├── 14-Labs/
├── 15-Cheat Sheets/
├── 16-Glossary/
├── 17-Resources/
├── 18-Blogs/
├── 19-Projects/
└── 20-Certification Notes/
```

---
# 📈 Progress Tracker

> Track your progress as you work through the Networking curriculum. A chapter is considered **complete** only after you have finished the notes, completed the hands-on labs, written a learning summary or blog post, and pushed your work to GitHub.

| Chapter | Notes | Labs | Blog | GitHub | Revision | Status |
|:--------|:-----:|:----:|:----:|:------:|:--------:|:------:|
| 📖 Introduction | ✅ | ⬜ | ⬜ | ✅ | ⬜ | ✅ |
| 🧩 Network Models | ✅ | ⬜ | ⬜ | ✅ | ⬜ | ✅ |
| 🖧 Network Devices | ✅ | ⬜ | ⬜ | ✅ | ⬜ | ✅ |
| 🔌 Network Media | ✅ | ⬜ | ⬜ | ✅ | ⬜ | ✅ |
| 🌍 IP Addressing | ✅ | ⬜ | ⬜ | ✅ | ⬜ | ✅ |
| 📡 Network Protocols | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 🚪 Ports & Services | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 🔀 Routing & Switching | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 🛠️ Network Services | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 🛡️ Network Security | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 📊 Network Monitoring | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 🔍 Network Scanning | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 📶 Wireless Networking | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| ☁️ Cloud Networking | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 🧪 Hands-on Labs | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| ⚡ Cheat Sheets | ⬜ | — | — | ⬜ | ⬜ | ⏳ |
| 📖 Glossary | ⬜ | — | — | ⬜ | ⬜ | ⏳ |
| 📚 Resources | ⬜ | — | — | ⬜ | ⬜ | ⏳ |
| 📝 Blogs & Learning Journal | ⬜ | — | ✅ | ⬜ | ⬜ | ⏳ |
| 🚀 Projects | ⬜ | ⬜ | ⬜ | ⬜ | ⬜ | ⏳ |
| 🎓 Certification Notes | ⬜ | ⬜ | — | ⬜ | ⬜ | ⏳ |

---

## 📊 Overall Progress

| Milestone | Progress |
|-----------|----------|
| 📖 Chapters Completed | **5 / 21** |
| 🧪 Labs Completed | **0 / Planned** |
| 🚀 Projects Completed | **0 / 8** |
| 📝 Blogs Written | **0 / 12+** |
| 💾 GitHub Commits | **5+** |
| 🔄 Revision Cycles | **0** |
| 🏆 Completion | **24%** |
---

## ✅ Definition of Completion

A chapter is considered complete only after all of the following are finished:

- ☑️ Read the chapter README
- ☑️ Read every topic note
- ☑️ Complete all practical labs
- ☑️ Practice with the recommended tools
- ☑️ Finish the TryHackMe/Packet Tracer/Home Lab exercises (where applicable)
- ☑️ Write a blog or learning summary
- ☑️ Commit your work to GitHub with a meaningful commit message
- ☑️ Review the chapter at least once

---

## 🏅 Milestones

| Achievement | Goal |
|-------------|------|
| 🌱 Beginner Network Explorer | Complete Chapters **00–04** |
| 🔧 Network Practitioner | Complete Chapters **05–09** |
| 🛡️ Network Defender | Complete Chapters **10–13** |
| 🧪 Hands-on Specialist | Finish all Labs and Projects |
| 📚 Knowledge Builder | Complete Cheat Sheets, Glossary, and Resources |
| 🎓 Certification Ready | Finish Certification Notes and complete the entire Networking section |

> **Remember:** The goal isn't just to check boxes—it's to build a deep understanding through reading, practicing, documenting, and reviewing. Consistent progress over time will lead to lasting expertise.

---

## 📝 How to Study

Follow this repeatable study loop for every chapter:

1. 📖 **Read the chapter README** to understand the big picture
2. 📓 **Read the detailed topic notes** inside each chapter
3. ✍️ **Take handwritten notes** — writing by hand improves retention
4. 🧪 **Complete the hands-on labs** provided in each chapter
5. 🚩 **Complete the related TryHackMe room** for practical reinforcement
6. 🖧 **Complete the Packet Tracer lab** to reinforce device/routing concepts
7. 📰 **Write one blog post** summarizing what you learned in your own words
8. 💾 **Commit your notes and labs to GitHub** to track your progress publicly
9. 🔁 **Review** previous chapters regularly using spaced repetition
10. ♻️ **Repeat** this loop for every chapter in the roadmap

> 🧠 **Consistency beats intensity.** A little every day will take you further than cramming once a week.

---

## ➡️ Next Section

Once you've completed this Networking section and checked off every chapter above, continue your journey to:

## 🐧 [03 - Linux](../03-Linux/README.md)

---

<div align="center">

**⭐ Master the network, and you master the battlefield of cybersecurity. ⭐**

</div>
