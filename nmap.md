# Nmap Mastery
## From Beginner to Advanced (Myanmar Edition)

> **စာရေးသူ:** Cybersecurity Instructor Team
> **ထုတ်ဝေသည့်နှစ်:** 2026
> **ဘာသာစကား:** မြန်မာ (Burmese)
> **Technical Terms:** English

---

## စာရေးသူ၏ မှတ်ချက် (Author's Note)

ဤစာအုပ်သည် Nmap Security Scanner ၏ ပြည့်စုံသော လက်စွဲစာအုပ်ဖြစ်ပါသည်။ အခြေခံမှစ၍ Professional အဆင့်အထိ အဆင့်ဆင့် လေ့လာနိုင်ရန် ရေးသားထားပါသည်။ ဤစာအုပ်တွင် ဖော်ပြထားသော အချက်အလက်များသည် Official Nmap Documentation, Nmap Network Scanning (Official Book by Gordon "Fyodor" Lyon), Nmap Reference Guide, NSE Documentation နှင့် အခြား ယုံကြည်စိတ်ချရသော ရင်းမြစ်များမှ ကိုးကားထားပါသည်။

> **အရေးကြီးသတိပေးချက် (Important Warning):** Nmap ကို သင်ပိုင်ဆိုင်သော သို့မဟုတ် ခွင့်ပြုချက်ရရှိထားသော Network များတွင်သာ အသုံးပြုပါ။ ခွင့်ပြုချက်မရှိဘဲ အခြားသူများ၏ System ကို Scan ပြုလုပ်ခြင်းသည် ဥပဒေချိုးဖောက်မှု ဖြစ်နိုင်ပါသည်။ ဤစာအုပ်သည် ပညာရေးနှင့် ခွင့်ပြုထားသော Security Testing အတွက်သာ ရည်ရွယ်ပါသည်။

---

## မာတိကာ (Table of Contents)

### အပိုင်း ၁ — အခြေခံအုတ်မြစ် (Foundations)

1. **Network Scanning မိတ်ဆက်** (Introduction to Network Scanning)
   - 1.1 Network Scanning ဆိုသည်မှာ
   - 1.2 Nmap ၏ သမိုင်းကြောင်း
   - 1.3 Nmap ၏ အရေးပါမှု
   - 1.4 Ethical Usage နှင့် ဥပဒေဆိုင်ရာ ကိစ္စရပ်များ

2. **TCP/IP အခြေခံများ** (Understanding TCP/IP)
   - 2.1 OSI Model နှင့် TCP/IP Model
   - 2.2 IPv4 Header Structure
   - 2.3 TCP Header နှင့် Three-Way Handshake
   - 2.4 UDP Protocol
   - 2.5 ICMP Protocol
   - 2.6 Port ဆိုသည်မှာ
   - 2.7 TCP Flags အသေးစိတ်

3. **Nmap အလုပ်လုပ်ပုံ** (How Nmap Works)
   - 3.1 Nmap ၏ Architecture
   - 3.2 Scan Phases (အဆင့်များ)
   - 3.3 Raw Packet များအသုံးပြုပုံ
   - 3.4 Nmap ၏ Data Files များ

4. **Nmap ထည့်သွင်းခြင်း** (Installing Nmap)
   - 4.1 Linux တွင် ထည့်သွင်းခြင်း
   - 4.2 Windows တွင် ထည့်သွင်းခြင်း
   - 4.3 macOS တွင် ထည့်သွင်းခြင်း
   - 4.4 Source Code မှ Compile လုပ်ခြင်း
   - 4.5 ထည့်သွင်းမှု စစ်ဆေးခြင်း

### အပိုင်း ၂ — Core Scanning

5. **Command Line အခြေခံများ** (Command Line Basics)
   - 5.1 Nmap Command Syntax
   - 5.2 Target Specification
   - 5.3 Port Specification
   - 5.4 Verbosity နှင့် Debugging

6. **Host Discovery** (Host Discovery)
   - 6.1 Ping Scan Techniques
   - 6.2 ARP Scan
   - 6.3 TCP SYN/ACK Ping
   - 6.4 UDP Ping
   - 6.5 ICMP Ping Types
   - 6.6 IP Protocol Ping
   - 6.7 Host Discovery Strategies

7. **Port Scanning Techniques** (Port Scanning Techniques)
   - 7.1 TCP SYN Scan (-sS)
   - 7.2 TCP Connect Scan (-sT)
   - 7.3 UDP Scan (-sU)
   - 7.4 TCP FIN/NULL/Xmas Scans
   - 7.5 TCP ACK Scan (-sA)
   - 7.6 TCP Window Scan (-sW)
   - 7.7 TCP Maimon Scan (-sM)
   - 7.8 TCP Idle Scan (-sI)
   - 7.9 IP Protocol Scan (-sO)
   - 7.10 FTP Bounce Scan (-b)
   - 7.11 Custom Scan Types (--scanflags)
   - 7.12 Scan Types Comparison Table

8. **Service & Version Detection** (Service and Version Detection)
   - 8.1 Version Detection နိဒါန်း
   - 8.2 -sV Option
   - 8.3 Version Detection Intensity
   - 8.4 Banner Grabbing
   - 8.5 RPC Grinding
   - 8.6 SSL/TLS Analysis
   - 8.7 nmap-service-probes Database

### အပိုင်း ၃ — Advanced Techniques

9. **OS Detection** (Operating System Detection)
   - 9.1 OS Detection နိဒါန်း
   - 9.2 -O Option
   - 9.3 TCP/IP Fingerprinting Methods
   - 9.4 IPv6 OS Detection
   - 9.5 OS Detection Accuracy
   - 9.6 nmap-os-db Database
   - 9.7 Submitting New Fingerprints

10. **Nmap Scripting Engine (NSE)** (Nmap Scripting Engine)
    - 10.1 NSE မိတ်ဆက်
    - 10.2 Script Architecture
    - 10.3 Script Categories
    - 10.4 Script Types & Phases
    - 10.5 Script Selection
    - 10.6 Script Arguments
    - 10.7 Safe Scripts
    - 10.8 Discovery Scripts
    - 10.9 Vulnerability Scripts
    - 10.10 Writing Custom Scripts
    - 10.11 Script Parallelism

11. **Timing & Performance** (Timing and Performance)
    - 11.1 Timing Templates (-T0 to -T5)
    - 11.2 Low-Level Timing Controls
    - 11.3 Performance Optimization
    - 11.4 Scan Time Reduction
    - 11.5 Congestion Control
    - 11.6 Multi-stage Scanning

12. **Firewall & IDS Evasion** (Firewall and IDS Evasion)
    - 12.1 Firewall Basics
    - 12.2 Determining Firewall Rules
    - 12.3 Fragmentation (-f, --mtu)
    - 12.4 Decoys (-D)
    - 12.5 Source Port Manipulation
    - 12.6 MAC Address Spoofing
    - 12.7 Idle Scan for Evasion
    - 12.8 Source Routing
    - 12.9 Proxies
    - 12.10 Timing-based Evasion

13. **Output Formats** (Output Formats)
    - 13.1 Interactive Output
    - 13.2 Normal Output (-oN)
    - 13.3 XML Output (-oX)
    - 13.4 Grepable Output (-oG)
    - 13.5 All Formats (-oA)
    - 13.6 Script Kiddie Output (-oS)
    - 13.7 Verbosity & Debugging
    - 13.8 Resuming Aborted Scans

14. **XML Processing** (XML Processing)
    - 14.1 Nmap XML Structure
    - 14.2 XML Output DTD
    - 14.3 Parsing XML with Scripts
    - 14.4 HTML Report Generation
    - 14.5 Database Output

### အပိုင်း ၄ — Practical Applications

15. **Practical Network Enumeration** (Practical Network Enumeration)
    - 15.1 Internal Network Scanning
    - 15.2 External Network Scanning
    - 15.3 Service Inventory
    - 15.4 Network Mapping
    - 15.5 Real-World Workflows

16. **Service-Specific Enumeration**

    - 16.1 Web Server Enumeration
    - 16.2 SMB Enumeration
    - 16.3 DNS Enumeration
    - 16.4 Email (SMTP) Enumeration
    - 16.5 FTP Enumeration
    - 16.6 SSH Enumeration
    - 16.7 Database Enumeration (MySQL)
    - 16.8 SSL/TLS Analysis

17. **Active Directory Enumeration** (Active Directory Enumeration)
    - 17.1 Domain Controller Discovery
    - 17.2 LDAP Enumeration
    - 17.3 Kerberos Enumeration
    - 17.4 SMB Share Enumeration
    - 17.5 AD-Specific NSE Scripts

18. **Vulnerability Detection** (Vulnerability Detection)
    - 18.1 Vulnerability Scanning Overview
    - 18.2 Using NSE for Vulnerability Detection
    - 18.3 EternalBlue (MS17-010)
    - 18.4 Heartbleed Detection
    - 18.5 Common Vulnerability Scanning
    - 18.6 CVE Lookup with Vulners

19. **Automation with Bash** (Bash Automation)
    - 19.1 Basic Bash Scripting with Nmap
    - 19.2 Bulk Scanning Scripts
    - 19.3 Parsing Output with awk/sed
    - 19.4 Scheduling Scans (Cron)
    - 19.5 Automated Reporting

20. **Automation with Python** (Python Automation)
    - 20.1 Python-nmap Library
    - 20.2 Parsing XML Output
    - 20.3 Building Custom Scanners
    - 20.4 Integration with Other Tools
    - 20.5 Web Dashboard

### အပိုင်း ၅ — Professional Practice

21. **Safe Security Assessment** (Safe Security Assessment)
    - 21.1 Rules of Engagement
    - 21.2 Scope Definition
    - 21.3 Risk Mitigation
    - 21.4 Scan Parameters for Safety

22. **Reporting** (Reporting)
    - 22.1 Professional Report Writing
    - 22.2 Executive Summary
    - 22.3 Technical Findings
    - 22.4 Remediation Recommendations
    - 22.5 Using Ndiff for Comparison

23. **Troubleshooting & Common Errors** (Troubleshooting and Common Errors)
    - 23.1 Permission Issues
    - 23.2 Network Issues
    - 23.3 False Positives vs False Negatives
    - 23.4 Scan Hangs
    - 23.5 Common Error Messages

24. **Best Practices** (Best Practices)
    - 24.1 Scanning Methodology
    - 24.2 Documentation
    - 24.3 Reducing False Positives
    - 24.4 Legal Compliance
    - 24.5 Tool Integration

25. **Lab Exercises** (Lab Exercises)
    - 25.1 Setting Up a Lab Environment
    - 25.2 Beginner Exercises (5 exercises)
    - 25.3 Intermediate Exercises (5 exercises)
    - 25.4 Advanced Exercises (5 exercises)
    - 25.5 Expert Challenges (5 exercises)

26. **Review Questions** (Review Questions)
    - 26.1 Beginner Level (20 questions)
    - 26.2 Intermediate Level (20 questions)
    - 26.3 Advanced Level (20 questions)

27. **Cheat Sheets** (Cheat Sheets)
    - 27.1 Command Quick Reference
    - 27.2 Port Scanning Methods Comparison
    - 27.3 NSE Script Categories
    - 27.4 Timing Templates
    - 27.5 Output Options

28. **Appendices** (Appendices)
    - A. Common Port Numbers
    - B. TCP Flags Reference
    - C. ICMP Types and Codes
    - D. Nmap Data Files Reference
    - E. Glossary of Terms
    - F. Bibliography and Further Reading

---

## အပိုင်း ၁ — အခြေခံအုတ်မြစ် (Foundations)

---

## အခန်း ၁ — Network Scanning မိတ်ဆက်

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Network Scanning ၏ အခြေခံသဘောတရားကို နားလည်မည်
- Nmap ၏ သမိုင်းကြောင်းနှင့် အရေးပါမှုကို သိရှိမည်
- Ethical Hacking တွင် Nmap ၏ အခန်းကဏ္ဍကို သဘောပေါက်မည်
- Nmap အသုံးပြုခြင်း၏ ဥပဒေဆိုင်ရာ ကဏ္ဍများကို သိရှိမည်

---

### 1.1 Network Scanning ဆိုသည်မှာ

**Network Scanning** ဆိုသည်မှာ Network တစ်ခုအတွင်းရှိ မည်သည့် Host များ Online ရှိသည်၊ မည်သည့် Port များ Open ဖြစ်သည်၊ မည်သည့် Service များ Run နေသည် စသည့် အချက်အလက်များကို စနစ်တကျ စုဆောင်းခြင်း လုပ်ငန်းစဉ် ဖြစ်သည်။

Network Scanning သည် **Ethical Hacking** သို့မဟုတ် **Penetration Testing** ၏ ပထမဆုံးနှင့် အရေးအကြီးဆုံး အဆင့်ဖြစ်သည်။ ဤအဆင့်ကို **Information Gathering** သို့မဟုတ် **Reconnaissance** (Recon) ဟုလည်း ခေါ်ဆိုသည်။

Network Scanning ကို အောက်ပါနယ်ပယ်များတွင် အသုံးပြုသည်:

| နယ်ပယ် | အသုံးပြုပုံ |
|---------|------------|
| **Security Auditing** | Network ၏ လုံခြုံရေးအားနည်းချက်များကို ရှာဖွေခြင်း |
| **Network Administration** | Network အတွင်းရှိ Device များ၏ Inventory ပြုလုပ်ခြင်း |
| **Compliance** | လုံခြုံရေးစံနှုန်းများနှင့် ကိုက်ညီမှုရှိမရှိ စစ်ဆေးခြင်း |
| **Troubleshooting** | Network ပြဿနာများ ရှာဖွေဖြေရှင်းခြင်း |
| **Monitoring** | Service Uptime နှင့် Host Status စောင့်ကြည့်ခြင်း |

---

### 1.2 Nmap ၏ သမိုင်းကြောင်း

**Nmap** (Network Mapper) ကို **Gordon Lyon** (Fyodor ဟု လူသိများ) မှ ၁၉၉၇ ခုနှစ်တွင် စတင်ဖန်တီးခဲ့သည်။ ပထမဆုံး Public Release ကို Phrack Magazine, Issue 51 တွင် "The Art of Port Scanning" ဆောင်းပါးအဖြစ် ထုတ်ဝေခဲ့သည်။

**အဓိက မှတ်တိုင်များ:**

- **1997**: Nmap 1.0 — Phrack Magazine တွင် ပထမဆုံးထုတ်ဝေ
- **2008**: Nmap 4.50 — Zenmap GUI စတင်ပါဝင်
- **2009**: Nmap 5.00 — NSE (Nmap Scripting Engine) စတင်မိတ်ဆက်
- **2012**: Nmap 6.00 — Full IPv6 Support, 300+ NSE Scripts
- **2016**: Nmap 7.00 — Major Update, 500+ NSE Scripts
- **2021**: Nmap 7.90 — 600+ NSE Scripts
- **2022**: Nmap 7.93 — Latest Major Version

Nmap သည် **Open Source** ဖြစ်ပြီး Nmap Public Source License (NPSL) အောက်တွင် ထုတ်ဝေထားသည်။ ယနေ့အထိ Security Professional သန်းပေါင်းများစွာ အသုံးပြုနေကြပြီး အခမဲ့ Network Scanning Tool များတွင် စံပြုအဖြစ် သတ်မှတ်ခံထားရသည်။

---

### 1.3 Nmap ၏ အရေးပါမှု

Nmap သည် အောက်ပါအကြောင်းများကြောင့် အရေးပါသည်:

**၁။ ပြည့်စုံမှု (Comprehensiveness):**
- Host Discovery — Network အတွင်းရှိ Live Host များရှာဖွေခြင်း
- Port Scanning — Open Port များရှာဖွေခြင်း
- Service/Version Detection — Service Version ဖော်ထုတ်ခြင်း
- OS Detection — Operating System ဖော်ထုတ်ခြင်း
- Script Engine — Custom Automation
- 600+ Built-in Scripts

**၂။ စွမ်းဆောင်ရည် (Performance):**
- ကြီးမားသော Network များကို လျင်မြန်စွာ Scan ပြုလုပ်နိုင်
- Congestion Control နှင့် Adaptive Timing
- Parallel Scanning

**၃။ Platform Support:**
- Linux, Windows, macOS, BSD, Solaris, AIX, AmigaOS စသည်ဖြင့် အမျိုးမျိုး
- Command-line နှင့် GUI (Zenmap) နှစ်မျိုးလုံး

**၄။ Community & Documentation:**
- Official Book (Nmap Network Scanning)
- Reference Guide
- Active Community
- Regular Updates

---

### 1.4 Ethical Usage နှင့် ဥပဒေဆိုင်ရာ ကိစ္စရပ်များ

> **WARNING — အရေးကြီးသတိပေးချက်**

Nmap အသုံးပြုခြင်းနှင့် ပတ်သက်၍ ဥပဒေဆိုင်ရာ ကိစ္စရပ်များမှာ အလွန်အရေးကြီးပါသည်:

**ခွင့်ပြုချက်မရှိဘဲ Port Scanning ပြုလုပ်ခြင်းသည် ရာဇဝတ်မှုဖြစ်နိုင်ပါသလား?**

တရားဝင်ခွင့်ပြုချက်မရှိဘဲ Port Scanning ပြုလုပ်ခြင်းကို နိုင်ငံအများစုတွင် တရားမ၀င်ဟု သတ်မှတ်နိုင်ပါသည်။ အောက်ပါအချက်များကို အထူးသတိပြုပါ:

- **ရေးသားထားသော ခွင့်ပြုချက် (Written Permission)** ရှိမှသာ Scan ပြုလုပ်ပါ
- Scan ပြုလုပ်မည့် Scope နှင့် Target များကို ကြိုတင်သဘောတူညီချက်ရယူပါ
- Third-party Cloud Service များကို ခွင့်ပြုချက်ရှိမှသာ Scan လုပ်ပါ
- **Scanme.nmap.org** ကို သာမန် Scan အနည်းငယ်သာ ပြုလုပ်ပါ — DoS Attack မလုပ်ပါနှင့်

**Port Scanning ကြောင့် Target Computer/Network ပျက်စီးနိုင်ပါသလား?**

- များသောအားဖြင့် Port Scan သည် Target ကို မပျက်စီးစေပါ
- သို့သော် Aggressive Scanning သည် အချို့သော Old Systems သို့မဟုတ် Fragile Network Devices များတွင် ပြဿနာဖြစ်စေနိုင်သည်
- Production Environment တွင် သတိထား၍ Scan ပြုလုပ်သင့်သည်

> **Best Practice:** အမြဲတမ်း Explicit Written Authorization ရယူပါ။ Scope, Timing, Techniques များကို Client နှင့် ကြိုတင်သဘောတူညီပါ။

---

### အကျဉ်းချုပ် (Summary)

- Network Scanning သည် Security Assessment ၏ ပထမဆုံးအဆင့်ဖြစ်သည်
- Nmap သည် ၁၉၉၇ ခုနှစ်မှစ၍ အသုံးပြုလာသော Open Source Network Scanner ဖြစ်သည်
- Nmap သည် Host Discovery, Port Scanning, Service Detection, OS Detection, Scripting စသည့် လုပ်ဆောင်ချက်များကို ဆောင်ရွက်နိုင်သည်
- Ethical Usage အတွက် အမြဲတမ်း Written Permission ရယူရန် လိုအပ်သည်

### Key Takeaways

| Key Point | Detail |
|-----------|--------|
| Nmap Creator | Gordon Lyon (Fyodor) |
| First Release | 1997 (Phrack 51) |
| License | NPSL (Open Source) |
| Test Target | scanme.nmap.org |
| Golden Rule | Written Permission Required |

---

## အခန်း ၂ — TCP/IP အခြေခံများ

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- TCP/IP Protocol Suite ၏ အခြေခံဖွဲ့စည်းပုံကို နားလည်မည်
- IPv4, TCP, UDP, ICMP Headers များကို သိရှိမည်
- TCP Three-Way Handshake လုပ်ငန်းစဉ်ကို သဘောပေါက်မည်
- Port အယူအဆကို နားလည်မည်
- TCP Flags တစ်ခုချင်းစီ၏ အခန်းကဏ္ဍကို သိရှိမည်

### ကြိုတင်လိုအပ်ချက်များ (Prerequisites)

- Networking အခြေခံသဘောတရား
- Binary/Hexadecimal နားလည်မှု (အနည်းအကျဉ်း)

---

### 2.1 OSI Model နှင့် TCP/IP Model

Network Protocols များကို နားလည်ရန် OSI Model နှင့် TCP/IP Model ကို သိရှိထားရန် လိုအပ်သည်။

**TCP/IP Model (4 Layers):**

```
+----------------------------------+
|  Application Layer    (Layer 4)  |  HTTP, SSH, DNS, SMTP, FTP
+----------------------------------+
|  Transport Layer      (Layer 3)  |  TCP, UDP
+----------------------------------+
|  Internet Layer       (Layer 2)  |  IP (IPv4, IPv6), ICMP, ARP
+----------------------------------+
|  Network Access Layer (Layer 1)  |  Ethernet, Wi-Fi
+----------------------------------+
```

**Encapsulation ဖြစ်စဉ်:**

```
[Ethernet Header][IP Header][TCP/UDP Header][Application Data][Ethernet Trailer]
```

Data သည် Application Layer မှ Network Access Layer သို့ ဆင်းသွားချိန်တွင် Layer တစ်ခုစီ၌ Header များ ထပ်ဆင့်ထည့်သွင်းခြင်းခံရသည်။ Nmap သည် ဤ Packet Structure ကို နားလည်ပြီး Raw Packets များကို တိုက်ရိုက် ဖန်တီးကိုင်တွယ်နိုင်သည်။

---

### 2.2 IPv4 Header Structure

IPv4 Header သည် 20 bytes (options မပါလျှင်) ရှိသည်။

```
    0                   1                   2                   3
    0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |Version|  IHL  |Type of Service|          Total Length         |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |         Identification        |Flags|      Fragment Offset    |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |  Time to Live |    Protocol   |         Header Checksum       |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                       Source Address                          |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                    Destination Address                        |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

**Nmap နှင့် သက်ဆိုင်သော Key Fields:**

| Field | Size | Nmap တွင် အသုံးပြုပုံ |
|-------|------|----------------------|
| TTL (Time to Live) | 8 bits | OS Detection တွင် Initial TTL ကိုကြည့်၍ OS ခန့်မှန်း |
| Protocol | 8 bits | IP Protocol Scan (-sO) တွင် အသုံးပြု |
| Flags (DF bit) | 3 bits | OS Detection တွင် Don't Fragment behavior စစ်ဆေး |
| Fragment Offset | 13 bits | Fragmentation (-f, --mtu) တွင် အသုံးပြု |
| Identification (IP ID) | 16 bits | Idle Scan (-sI) တွင် Zombie Host ၏ IP ID ကို စောင့်ကြည့် |

---

### 2.3 TCP Header နှင့် Three-Way Handshake

**TCP Header Structure:**

```
    0                   1                   2                   3
    0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |          Source Port          |       Destination Port        |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                        Sequence Number                        |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                    Acknowledgment Number                      |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |  Data |           |U|A|P|R|S|F|                               |
   | Offset| Reserved  |R|C|S|S|Y|I|            Window             |
   |       |           |G|K|H|T|N|N|                               |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |           Checksum            |         Urgent Pointer        |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

**TCP Three-Way Handshake (Full Lifecycle):**

```
Client                              Server
  |                                    |
  |-------- SYN (Seq=X) -------------->|  Step 1: Client sends SYN
  |                                    |
  |<---- SYN+ACK (Seq=Y, Ack=X+1) ----|  Step 2: Server responds
  |                                    |
  |-------- ACK (Ack=Y+1) ----------->|  Step 3: Client acknowledges
  |                                    |
  |        [Connection Established]    |
  |                                    |
  |-------- RST (Reset) -------------->|  Connection Termination
```

Nmap ၏ SYN Scan (-sS) သည် Three-Way Handshake ကို အပြည့်အစုံမပြုလုပ်ပဲ Step 2 ပြီးနောက် RST ပို့၍ Connection ကို ဖြတ်တောက်သည်။ ဤနည်းကို **Half-Open Scan** ဟုခေါ်သည်။

---

### 2.4 UDP Protocol

**UDP (User Datagram Protocol)** သည် Connectionless Protocol ဖြစ်သည်:

- Three-Way Handshake မရှိ — ချက်ချင်း Data ပို့သည်
- Header သည် 8 bytes သာရှိ (TCP က 20 bytes)
- Reliability Guarantee မရှိ — Packet Loss ဖြစ်နိုင်
- DNS (53), SNMP (161), TFTP (69), DHCP (67) တို့တွင် အသုံးပြု

**UDP Header Structure:**

```
    0                   1                   2                   3
    0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |          Source Port          |       Destination Port        |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |            Length             |           Checksum            |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

**UDP Scan တွင် Nmap ၏ Response Logic:**

| Nmap ပို့သည့် Packet | Response | Nmap ၏ ဆုံးဖြတ်ချက် |
|------------------------|----------|-------------------|
| UDP Probe | Response မရှိ | Port Open/Filtered |
| UDP Probe | ICMP Port Unreachable (Type 3, Code 3) | Port Closed |
| UDP Probe | UDP Response | Port Open |

---

### 2.5 ICMP Protocol

**ICMP (Internet Control Message Protocol)** သည် Error Reporting နှင့် Diagnostic အတွက်ဖြစ်သည်။

**ICMP Header Structure:**

```
    0                   1                   2                   3
    0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |     Type      |     Code      |           Checksum            |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
   |                        (Type-specific)                        |
   +-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

**Nmap တွင် အသုံးများသော ICMP Types:**

| Type | Code | ဖော်ပြချက် | Nmap တွင် အသုံးပြုပုံ |
|------|------|-----------|----------------------|
| 0 | 0 | Echo Reply | Ping Sweep (-PE) အတွက် တုံ့ပြန်မှု |
| 3 | 0 | Network Unreachable | - |
| 3 | 1 | Host Unreachable | - |
| 3 | 3 | Port Unreachable | UDP Scan တွင် Port Closed ဟုသတ်မှတ် |
| 8 | 0 | Echo Request | Ping Sweep (-PE) အတွက် ပို့သည့် Packet |
| 13 | 0 | Timestamp Request | Timestamp Ping (-PP) |

---

### 2.6 Port ဆိုသည်မှာ

**Port** ဆိုသည်မှာ Network Communication အတွက် Endpoint တစ်ခုဖြစ်သည်။ Port သည် 16-bit Integer (0-65535) ဖြစ်ပြီး IP Address နှင့် Port Number ပေါင်းစပ်၍ မည်သည့် Service နှင့် ဆက်သွယ်မည်ကို သတ်မှတ်သည်။

**Port Range အမျိုးအစားများ:**

| Range | Name | Usage |
|-------|------|-------|
| 0-1023 | Well-Known / System Ports | Standard Services (HTTP=80, SSH=22) |
| 1024-49151 | Registered Ports | Application-specific |
| 49152-65535 | Dynamic / Private Ports | Ephemeral, Client-side |

**Total TCP/UDP Ports:** 65535 × 2 = 131,070

**Nmap Default Scan:** ပုံမှန်အားဖြင့် Port 1000 ခန့်ကိုသာ Scan လုပ်သည် (nmap-services file တွင် အသုံးအများဆုံးအဖြစ် သတ်မှတ်ထားသော Port များ)။ Port အားလုံးကို Scan လုပ်ရန် `-p-` လိုအပ်သည်။

---

### 2.7 TCP Flags အသေးစိတ်

TCP Header တွင် Control Flags (၆) ခုပါဝင်သည်:

| Flag | အမည် | တန်ဖိုး | ရှင်းလင်းချက် |
|------|------|--------|--------------|
| **SYN** | Synchronize | Set in step 1 | Connection တည်ဆောက်ရန် ကမ်းလှမ်းခြင်း |
| **ACK** | Acknowledgment | Set in step 2,3 | Data လက်ခံရရှိကြောင်း အတည်ပြုခြင်း |
| **RST** | Reset | Connection reset | Connection ကို ချက်ချင်းဖြတ်တောက်ခြင်း |
| **FIN** | Finish | Connection end | Connection ကို ပုံမှန်အဆုံးသတ်ခြင်း |
| **PSH** | Push | Data push | Data ကို Buffer မထားပဲ ချက်ချင်းပို့ |
| **URG** | Urgent | Urgent data | အရေးပေါ် Data ညွှန်ပြခြင်း |

**Nmap Scan Types နှင့် Flags ဆက်စပ်မှု:**

| Scan Type | Flag ပို့သည့် Packet | Open Port Response | Closed Port Response |
|-----------|----------------------|-------------------|---------------------|
| SYN (-sS) | SYN | SYN+ACK | RST |
| TCP Connect (-sT) | SYN (Full Handshake) | SYN+ACK→ACK→RST | RST |
| FIN (-sF) | FIN | No Response | RST |
| NULL (-sN) | None | No Response | RST |
| XMAS (-sX) | FIN+PSH+URG | No Response | RST |
| ACK (-sA) | ACK | RST (or no response) | RST |
| Maimon (-sM) | FIN+ACK | No Response | RST |

> **မှတ်ချက်:** FIN, NULL, XMAS, Maimon Scan များသည် Windows Target များတွင် များသောအားဖြင့် အလုပ်မလုပ်ပါ။ Windows သည် RFC 793 ကို အတိအကျမလိုက်နာပဲ RST Response ပြန်ပေးတတ်သောကြောင့်ဖြစ်သည်။

---

### အကျဉ်းချုပ် (Summary)

- TCP/IP Model တွင် Application, Transport, Internet, Network Access ဟူ၍ Layer ၄ ခုရှိသည်
- TCP သည် Connection-oriented Protocol ဖြစ်ပြီး Three-Way Handshake (SYN → SYN-ACK → ACK) ကို အသုံးပြုသည်
- UDP သည် Connectionless Protocol ဖြစ်ပြီး Header 8 bytes သာရှိသည်
- ICMP သည် Error Reporting နှင့် Diagnostic အတွက် အသုံးပြုသည်
- Port 65535 ခုရှိပြီး 0-1023 သည် Well-Known Ports ဖြစ်သည်
- TCP Flags (SYN, ACK, RST, FIN, PSH, URG) တို့သည် Nmap ၏ Scan Type များအတွက် အခြေခံဖြစ်သည်

### Key Takeaways

| Concept | Detail |
|---------|--------|
| TCP Handshake | SYN → SYN-ACK → ACK |
| UDP Characteristic | Connectionless, 8-byte header |
| Total Ports | 65,535 per protocol |
| Nmap Default Ports | ~1,000 most common |
| ICMP Port Unreachable | Type 3, Code 3 |

---

## အခန်း ၃ — Nmap အလုပ်လုပ်ပုံ

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Nmap ၏ Internal Architecture ကို နားလည်မည်
- Scan Phases များ၏ အဆင့်ဆင့်လုပ်ဆောင်ချက်ကို သိရှိမည်
- Raw Packet များအသုံးပြုပုံကို သဘောပေါက်မည်
- Nmap ၏ Data Files များကို နားလည်မည်

---

### 3.1 Nmap ၏ Architecture

Nmap တွင် အဓိက အစိတ်အပိုင်း (၄) ခုပါဝင်သည်:

1. **Core Scan Engine** — Host Discovery, Port Scanning, OS Detection, Version Detection အတွက် Core Logic
2. **Nmap Scripting Engine (NSE)** — Lua-based Scripting Engine
3. **Nping** — Packet Generation Tool (Nmap Suite ထဲပါဝင်)
4. **Ncat** — Network Connector/Utility (Nmap Suite ထဲပါဝင်)

```
+----------------------------------------------------------+
|                   Nmap Architecture                      |
+----------------------------------------------------------+
|  User Interface (CLI / Zenmap GUI)                       |
+----------------------------------------------------------+
|  Scan Controller                                         |
|    - Target Resolution                                   |
|    - Host State Management                               |
|    - Scan Phase Orchestration                            |
+----------------------------------------------------------+
|  Core Engine                                             |
|    +------------------+  +-----------------------------+ |
|    | Port Scanner     |  | OS Detection Engine         | |
|    | (SYN, TCP, UDP)  |  | (TCP/IP Fingerprinting)     | |
|    +------------------+  +-----------------------------+ |
|    | Host Discovery   |  | Version Detection Engine    | |
|    | (ICMP, ARP, TCP) |  | (Service Probing)           | |
|    +------------------+  +-----------------------------+ |
+----------------------------------------------------------+
|  NSE (Nmap Scripting Engine) — Lua Runtime              |
+----------------------------------------------------------+
|  Packet Layer                                            |
|    - Raw Socket Interface                                |
|    - Npcap/WinPcap (Windows)                             |
|    - libpcap (Unix)                                      |
+----------------------------------------------------------+
```

---

### 3.2 Scan Phases (အဆင့်များ)

Nmap Scan တစ်ခုတွင် အောက်ပါ Phases (အဆင့်) များ ပါဝင်သည်:

```
Phase 1: Target Enumeration
  ├── DNS Resolution (Domain → IP)
  ├── Target List Expansion (Range, Subnet)
  └── Target Deduplication & Sorting

Phase 2: Host Discovery (Ping Scanning)
  ├── ARP Ping (Local Network)
  ├── ICMP Echo Request
  ├── TCP SYN to specific ports
  ├── TCP ACK to specific ports
  ├── UDP Probe
  └── Result: Live Hosts List

Phase 3: Reverse DNS Resolution
  └── IP → Hostname (if enabled)

Phase 4: Port Scanning
  ├── SYN Scan (default, privileged)
  ├── Connect Scan (fallback, unprivileged)
  ├── UDP Scan (if requested)
  └── Result: Open/Closed/Filtered Ports

Phase 5: Service/Version Detection
  ├── Probe sending
  ├── Response matching
  ├── SSL detection & unwrapping
  └── RPC grinding

Phase 6: OS Detection
  ├── TCP/IP Stack Probing
  ├── Response Analysis
  └── Fingerprint Matching

Phase 7: NSE Script Scanning
  ├── Pre-scanning scripts
  ├── Host scripts
  ├── Service scripts
  └── Post-scanning scripts

Phase 8: Traceroute (if -A or --traceroute)

Phase 9: Output Generation
  ├── Interactive (stdout)
  ├── File Output (-oN, -oX, -oG)
  └── Summary
```

Host Discovery ကို **Ping Scan** ဟုလည်း ခေါ်သည်။ `-Pn` Option သည် Phase 2 ကို Skip လုပ်ပြီး Host အားလုံးကို Online ဟု ယူဆကာ Port Scanning သို့ တိုက်ရိုက်ဆက်လုပ်သည်။

---

### 3.3 Raw Packet များအသုံးပြုပုံ

Nmap ၏ အဓိကထူးခြားချက်မှာ **Raw IP Packets** များကို တိုက်ရိုက်ဖန်တီး၍ Network ပေါ်သို့ ပို့နိုင်ခြင်းဖြစ်သည်။

**Raw Socket လိုအပ်သည့် Scan Type များ:**
- SYN Scan (-sS)
- FIN/NULL/XMAS Scans
- ACK Scan (-sA)
- Window Scan (-sW)
- Maimon Scan (-sM)
- Idle Scan (-sI)
- IP Protocol Scan (-sO)
- OS Detection (-O)
- UDP Scan (-sU)

**Non-raw Scan Type:**
- TCP Connect Scan (-sT) — OS ၏ connect() system call ကို အသုံးပြု

> **Note:** Raw Socket သုံးရန် Linux/Unix တွင် root privileges (sudo) လိုအပ်သည်။ Windows တွင် Administrator privileges လိုအပ်သည်။ Privileges မရှိပါက Nmap သည် Connect Scan (-sT) သို့ Auto-fallback လုပ်သည်။

---

### 3.4 Nmap ၏ Data Files များ

Nmap သည် အောက်ပါ Data Files များကို အသုံးပြုသည်:

| File | Path | Purpose |
|------|------|---------|
| `nmap-services` | `/usr/share/nmap/` | Port → Service mapping, frequency data |
| `nmap-service-probes` | `/usr/share/nmap/` | Version detection probes and match rules |
| `nmap-os-db` | `/usr/share/nmap/` | OS fingerprint database |
| `nmap-mac-prefixes` | `/usr/share/nmap/` | MAC address → Vendor mapping |
| `nmap-protocols` | `/usr/share/nmap/` | IP protocol numbers |
| `nmap-rpc` | `/usr/share/nmap/` | SunRPC program numbers |
| `nse/` | `/usr/share/nmap/scripts/` | NSE Scripts directory |

ဤ Data Files များကို မိမိကိုယ်ပိုင် Customize လုပ်နိုင်ပြီး `--datadir` Option ဖြင့် Custom Directory သတ်မှတ်နိုင်သည်။

---

### အကျဉ်းချုပ် (Summary)

- Nmap Architecture တွင် Core Engine, NSE, Nping, Ncat တို့ပါဝင်သည်
- Scan တစ်ခုတွင် Phases ၉ ဆင့်ရှိသည်
- Raw Socket Scan အတွက် root/administrator privileges လိုအပ်
- Nmap သည် Data Files များမှတစ်ဆင့် Service, OS, MAC Vendor အချက်အလက်များကို ရယူသည်

### Key Takeaways

| Concept | Detail |
|---------|--------|
| Scan Phases | 9 phases (Target Enum → Output) |
| Raw Socket | Required for most advanced scans |
| Default Port List | nmap-services file |
| Privilege Requirement | root/Administrator for raw scans |

---

## အခန်း ၄ — Nmap ထည့်သွင်းခြင်း (Installing Nmap)

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Linux, Windows, macOS တွင် Nmap ထည့်သွင်းနည်းကို သိရှိမည်
- Source Code မှ Compile လုပ်နည်းကို နားလည်မည်
- ထည့်သွင်းမှု အောင်မြင်ကြောင်း စစ်ဆေးနိုင်မည်
- Nmap ကို ဖယ်ရှားနည်းကို သိရှိမည်

---

### 4.1 Linux တွင် ထည့်သွင်းခြင်း

**စစ်ဆေးခြင်း — Nmap ရှိပြီးသားလား:**

```bash
nmap --version
# or
which nmap
```

**Kali Linux / Parrot OS:**
Penetration Testing Distribution များတွင် Nmap သည် Pre-installed ပါဝင်ပြီးဖြစ်သည်။ GUI Menu ၏ Information Gathering ကဏ္ဍတွင် ရှာနိုင်သည်။

**Debian/Ubuntu နှင့် Derivatives:**

```bash
sudo apt update
sudo apt install nmap
```

**RPM-based (Red Hat, Fedora, CentOS, SUSE):**

```bash
# Using yum
sudo yum install nmap

# Using dnf (Fedora 22+)
sudo dnf install nmap
```

**Arch Linux:**

```bash
sudo pacman -S nmap
```

**ထည့်သွင်းပြီးနောက် စစ်ဆေးခြင်း:**

```bash
nmap -V
# Output: Nmap version 7.93 ( https://nmap.org )
```

---

### 4.2 Windows တွင် ထည့်သွင်းခြင်း

**နည်းလမ်း ၁ — Self-Installer (.exe):**

1. https://nmap.org/download.html သို့သွားပါ
2. "Latest stable release self-installer" ကို Download လုပ်ပါ
3. Installer ကို Run ပါ (Administrator အဖြစ်)
4. Installation Options များ:
   - Nmap Core Files (မဖြစ်မနေ)
   - Npcap (Packet Capture Driver — လိုအပ်)
   - Zenmap GUI (Optional)

**နည်းလမ်း ၂ — Command-line Zip Binaries:**

1. Zip ဖိုင်ကို Download လုပ်၍ Extract လုပ်ပါ
2. Extract လုပ်ထားသော Directory ကို System PATH တွင် ထည့်ပါ
3. Command Prompt တွင် `nmap` ဟု run နိုင်ပါပြီ

**Windows တွင် Nmap Run ရန်:**

```
C:\> nmap --version
C:\> nmap scanme.nmap.org
```

> **Note:** Windows တွင် Nmap ကို Administrator Command Prompt မှ Run ရန် လိုအပ်နိုင်သည်။ Raw Socket Access အတွက် Npcap Driver ကို Install လုပ်စဉ် ထည့်သွင်းရန် သေချာပါစေ။

---

### 4.3 macOS တွင် ထည့်သွင်းခြင်း

**နည်းလမ်း ၁ — Executable Installer (.dmg):**

1. nmap.org/download.html မှ Mac OS X installer ကို Download လုပ်ပါ
2. .dmg ဖိုင်ကို Open ၍ Installer ကို Run ပါ
3. Apple Gatekeeper က Block လုပ်ပါက System Preferences → Security & Privacy တွင် Allow လုပ်ပါ

**နည်းလမ်း ၂ — Homebrew:**

```bash
brew install nmap
```

**နည်းလမ်း ၃ — MacPorts:**

```bash
sudo port install nmap
```

**စစ်ဆေးခြင်း:**

```bash
nmap --version
```

---

### 4.4 Source Code မှ Compile လုပ်ခြင်း

Source Code မှ Compile လုပ်လိုပါက:

```bash
# 1. Download source code
wget https://nmap.org/dist/nmap-7.93.tar.bz2

# 2. Extract
bzip2 -cd nmap-7.93.tar.bz2 | tar xvf -

# 3. Enter directory
cd nmap-7.93

# 4. Configure
./configure

# 5. Build
make

# 6. Install (as root)
sudo make install
```

**Custom Configure Options:**

```bash
# Without Zenmap GUI
./configure --without-zenmap

# Custom install prefix
./configure --prefix=/opt/nmap

# With OpenSSL (for SSL/TLS analysis)
./configure --with-openssl=/usr/local/ssl
```

**Source Code Integrity စစ်ဆေးခြင်း:**
Nmap Download Page တွင် SHA256 checksums နှင့် GPG signatures များရှိသည်။ Download လုပ်ထားသော ဖိုင်၏ တရားဝင်မှုကို စစ်ဆေးနိုင်သည်။

---

### 4.5 Nmap ကို ဖယ်ရှားခြင်း (Removing Nmap)

**Linux (Package Manager):**

```bash
# Debian/Ubuntu
sudo apt remove nmap
sudo apt purge nmap      # Config files ပါ ဖယ်ရှား

# RPM-based
sudo yum remove nmap
```

**Source Compile မှ ဖယ်ရှားခြင်း:**

```bash
sudo make uninstall       # Source directory ထဲမှ
```

**Windows:**

Control Panel → Programs and Features မှ Nmap ကို Uninstall လုပ်နိုင်သည်။ Npcap ကိုလည်း သီးခြားဖယ်ရှားရန် လိုအပ်နိုင်သည်။

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 4.1: Install & Verify**

```bash
# Step 1: Install Nmap on your system
# (Use the appropriate method above)

# Step 2: Verify version
nmap -V

# Step 3: Display help
nmap --help | head -30

# Step 4: Run a test scan
nmap -v scanme.nmap.org
```

---

### အကျဉ်းချုပ် (Summary)

| Platform | Method | Command |
|----------|--------|---------|
| Debian/Ubuntu | apt | `sudo apt install nmap` |
| Fedora/RHEL | yum/dnf | `sudo yum install nmap` |
| Arch | pacman | `sudo pacman -S nmap` |
| macOS | Homebrew | `brew install nmap` |
| Windows | Installer | Download from nmap.org |
| Source | Compile | `./configure && make && sudo make install` |
| Verify | Version check | `nmap -V` |

### Key Takeaways

- Kali Linux တွင် Pre-installed ပါဝင်သည်
- Windows တွင် Npcap Driver လိုအပ်သည်
- Source Compile အတွက် C/C++ compiler, make, libpcap တို့လိုအပ်သည်
- `nmap -V` ဖြင့် Installation အောင်မြင်ကြောင်း စစ်ဆေးနိုင်သည်

---

## အပိုင်း ၂ — Core Scanning

---

## အခန်း ၅ — Command Line အခြေခံများ (Command Line Basics)

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Nmap Command Syntax ကို ကောင်းစွာနားလည်မည်
- Target Specification နည်းလမ်းအားလုံးကို ကျွမ်းကျင်မည်
- Port Specification နည်းလမ်းများကို သိရှိမည်
- Verbosity နှင့် Debugging Options များကို အသုံးပြုနိုင်မည်

---

### 5.1 Nmap Command Syntax

Nmap ၏ အခြေခံ Syntax မှာ:

```
nmap [Scan Type...] [Options] {target specification}
```

**ဥပမာ:**

```bash
nmap -sS -sV -p 1-1000 -T4 192.168.1.1
#    └───┬───┘ └─┬─┘ └────┬────┘ └──────────┬──────────┘
#   Scan Type   Options   Port Spec     Target
```

**Command Line တွင် အသုံးပြုနိုင်သော အမျိုးအစားများ:**

1. **Scan Techniques:** `-sS`, `-sT`, `-sU`, `-sA`, `-sN`, `-sF`, `-sX`, `-sM`, `-sI`, `-sO`, `-sW`
2. **Options:** Timing (`-T`), Output (`-o`), Evasion (`-D`, `-f`), Scripts (`--script`)
3. **Target:** IP, Domain, Range, Subnet, File

---

### 5.2 Target Specification

Target သတ်မှတ်နိုင်သော နည်းလမ်းများ:

**Command:**
```
nmap 10.0.0.1
nmap www.example.com
nmap 192.168.10.0/24
nmap 10.1.1.5-100
nmap 10.1.1.3 10.1.1.6 10.1.1.8
nmap -iL targets.txt
nmap -iR 10
nmap 192.168.1.0/24 --exclude 192.168.1.1
nmap 192.168.1.0/24 --excludefile exclude.txt
```

| Option | Description | Example |
|--------|-------------|---------|
| Single IP | IP တစ်ခုတည်း | `nmap 10.0.0.1` |
| Domain | Domain name | `nmap scanme.nmap.org` |
| CIDR | Subnet mask ဖြင့် | `nmap 192.168.10.0/24` |
| Range | IP range | `nmap 10.1.1.5-100` |
| Multiple | Space ခြား၍ | `nmap 10.1.1.3 10.1.1.6 10.1.1.8` |
| File | File ထဲမှ ဖတ် | `nmap -iL targets.txt` |
| Random | Random targets | `nmap -iR 10` |
| Exclude | ချန်လှပ် | `nmap --exclude 192.168.1.1` |
| Exclude File | File ထဲမှ ချန်လှပ် | `nmap --excludefile exclude.txt` |

> **Common Mistake:** `-iR` ကို သုံးပါက Random Internet Host များကို Scan လုပ်မိမည်။ ခွင့်ပြုချက်မရှိပဲ မသုံးသင့်ပါ။

---

### 5.3 Port Specification

**Command Syntax:**

```
nmap -p [port-spec] [target]
```

| Specification | Command | Description |
|---------------|---------|-------------|
| Single Port | `-p 80` | Port 80 တစ်ခုတည်း |
| Port Range | `-p 20-25` | 20 မှ 25 အထိ |
| Multiple | `-p 80,443,8080` | Port စာရင်း |
| All Ports | `-p-` | Port 1-65535 အားလုံး |
| Fast Scan | `-F` | Top 100 ports |
| Top Ports | `--top-ports 100` | အသုံးအများဆုံး 100 |
| By Name | `-p http,https,ssh` | Service အမည်ဖြင့် |
| Protocol Mix | `-p U:53,T:22` | UDP port 53, TCP port 22 |
| Exclude | `-p- --exclude-ports 22,80` | Port 22,80 မှလွဲ၍ |

**Port Scan Order:**

```bash
# Sequential (not randomized)
nmap -r -p 1-100 192.168.1.1

# Default: Randomized
nmap -p 1-100 192.168.1.1
```

`-r` Option ဖြင့် Port များကို နံပါတ်စဉ်အတိုင်း Scan လုပ်နိုင်သည်။ ပုံမှန်အားဖြင့် Nmap သည် Port များကို Randomize လုပ်၍ Scan လုပ်သဖြင့် IDS Detection မှ ရှောင်တိမ်းနိုင်သည်။

---

### 5.4 Verbosity နှင့် Debugging

**Verbosity Levels:**

```bash
nmap -v target      # Verbose — scan progress ပြသ
nmap -vv target     # Very verbose — ပိုမိုအသေးစိတ်
nmap -v3 target     # Debugging level 3
nmap -d target      # Debugging mode
nmap -d2 target     # Debugging level 2
```

| Option | Level | Description |
|--------|-------|-------------|
| (none) | Default | Normal output |
| `-v` | Verbose | Scan progress, open ports during scan |
| `-vv` | Very Verbose | Additional timing/firewall info |
| `-d` | Debug | Debugging output |
| `-d2` | Debug L2 | More detailed debugging |
| `-d3` | Debug L3 | Even more detailed |
| `--packet-trace` | Packet | Show every packet sent/received |

**အသုံးပြုပုံ:**

- `-v`: Long-running scan များတွင် progress ကြည့်ရန်
- `-d`: Scan အလုပ်မလုပ်သည့်အခါ troubleshooting အတွက်
- `--packet-trace`: Packet-level analysis အတွက်

> **Tip:** Verbose mode သည် Scan Performance ကို အနည်းငယ်လျော့နိုင်သည်။ Production Scan တွင် default (no -v) ဖြင့်သုံး၍ ရလဒ်ကို File Output ယူခြင်းက ပိုကောင်းသည်။

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 5.1: Target & Port Specification**

```bash
# 1. Scan single IP
nmap 192.168.1.1

# 2. Scan with specific ports
nmap -p 22,80,443 192.168.1.1

# 3. Scan range with verbose
nmap -v -p 1-100 192.168.1.1

# 4. Scan all ports for known subnet
nmap -p- 192.168.1.0/24 --exclude 192.168.1.1,192.168.1.254

# 5. Check progress of long scan
nmap -vv -p- scanme.nmap.org
```

---

### အကျဉ်းချုပ် (Summary)

| Concept | Key Commands |
|---------|-------------|
| Single Target | `nmap IP` |
| Subnet | `nmap CIDR` |
| Range | `nmap IP1-IP2` |
| All Ports | `nmap -p-` |
| Top Ports | `nmap --top-ports N` |
| Verbose | `nmap -v`, `-vv` |
| Debug | `nmap -d` |

---

## အခန်း ၆ — Host Discovery

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Host Discovery ၏ နည်းလမ်းအားလုံးကို သိရှိမည်
- Ping Scan Techniques များကို ကျွမ်းကျင်မည်
- Network အခြေအနေအလိုက် သင့်လျော်သော Host Discovery Method ရွေးချယ်နိုင်မည်
- DNS Resolution ကို ထိန်းချုပ်နိုင်မည်

---

### 6.1 Host Discovery မိတ်ဆက်

Host Discovery (Ping Scanning) သည် Network တစ်ခုအတွင်းရှိ **မည်သည့် Host များ Online ဖြစ်သည်** ကို ရှာဖွေသည့် လုပ်ငန်းစဉ်ဖြစ်သည်။ Nmap ၏ Default အပြုအမှုမှာ Port Scan မစတင်မီ Host Discovery ပြုလုပ်ရန်ဖြစ်သည်။

**Default Host Discovery Process:**
Nmap သည် Local Network တွင် ARP ကိုလည်းကောင်း၊ Remote Network တွင် ICMP Echo Request, TCP SYN (port 443), TCP ACK (port 80), ICMP Timestamp Request တို့ကို ပေါင်းစပ်၍ Host Discovery ပြုလုပ်သည်။

---

### 6.2 List Scan (-sL)

**Command:**
```
nmap -sL 192.168.1.0/24
```

**Purpose:**
Target List ကိုသာ ဖန်တီးပြီး DNS Resolution ပြုလုပ်သည်။ Port Scan မလုပ်ပါ။

**How it works internally:**
Nmap သည် Target IP list ကို Expand လုပ်ပြီး Reverse DNS လုပ်ကာ Hostname များကို ပြသသည်။ Packet တစ်စုံတစ်ရာ မပို့ပါ။

**When to use:**
Scan မစတင်မီ Target List အတိအကျကို စစ်ဆေးလိုသည့်အခါ။ မှားယွင်းသော Target များကို ရှောင်ရှားရန်။

---

### 6.3 Ping Scan / No Port Scan (-sn)

**Command:**
```
nmap -sn 192.168.1.0/24
```

**Purpose:**
Host Discovery သာပြုလုပ်ပြီး Port Scan မလုပ်ပါ။

**How it works internally:**
Local Network အတွက် ARP Request ပို့သည်။ Remote Network အတွက် ICMP Echo + TCP SYN (443) + TCP ACK (80) + ICMP Timestamp ပေါင်းစပ်၍ ပို့သည်။

**Sample output:**
```
Nmap scan report for 192.168.1.1
Host is up (0.0032s latency).
MAC Address: XX:XX:XX:XX:XX:XX (Manufacturer)

Nmap scan report for 192.168.1.5
Host is up (0.0051s latency).
MAC Address: YY:YY:YY:YY:YY:YY (Manufacturer)

Nmap done: 256 IP addresses (4 hosts up) scanned in 3.78 seconds
```

**Advantages:**
- မြန်ဆန် — Port Scan မပါဝင်သောကြောင့်
- Network တစ်ခုလုံး၏ Live Host အရေအတွက်ကို လျင်မြန်စွာ သိရှိနိုင်
- MAC Address နှင့် Manufacturer အချက်အလက်ပါရရှိနိုင် (Local Network တွင်)

---

### 6.4 TCP SYN Ping (-PS)

**Command:**
```
nmap -PS22-25,80,443,3389 192.168.1.0/24
```

**Purpose:**
TCP SYN Packet ကို သတ်မှတ်ထားသော Port များသို့ပို့၍ Host Discovery ပြုလုပ်သည်။

**How it works internally:**
TCP SYN ကို Port သို့ပို့ပြီး SYN-ACK (သို့မဟုတ်) RST Response ရရှိပါက Host Online ဟုသတ်မှတ်သည်။

**Default Port:** 443 (အသုံးပြုသူက Port မသတ်မှတ်လျှင်)

**When to use:**
Firewall က ICMP ကို Block လုပ်ထားသော်လည်း TCP ကိုခွင့်ပြုထားသည့် Public Network များတွင်။ အလွန်အသုံးဝင်သည်။

---

### 6.5 TCP ACK Ping (-PA)

**Command:**
```
nmap -PA80,443 192.168.1.0/24
```

**Purpose:**
TCP ACK Packet ကို ပို့၍ Host Discovery ပြုလုပ်သည်။ RST Response ရပါက Host Online ဟု သတ်မှတ်သည်။

**Default Port:** 80

**When to use:**
SYN Ping ထက် Firewall ကို ပိုမိုကျော်လွှားနိုင်ခြေ ရှိသည့်အခါ။

---

### 6.6 UDP Ping (-PU)

**Command:**
```
nmap -PU161,53 192.168.1.0/24
```

**Purpose:**
UDP Packet ကို ပို့၍ Host Discovery ပြုလုပ်သည်။ ICMP Port Unreachable Response ရရှိပါက Host Online ဟု သတ်မှတ်သည်။

---

### 6.7 ICMP Ping Types (-PE, -PP, -PM)

```bash
nmap -PE 192.168.1.0/24    # ICMP Echo Request
nmap -PP 192.168.1.0/24    # ICMP Timestamp Request
nmap -PM 192.168.1.0/24    # ICMP Netmask Request
```

**When to use:**
Internal Network တွင် ICMP ကို Block မထားသည့်အခါ။ `-PE` သည် အရိုးရှင်းဆုံးနှင့် အသုံးအများဆုံးဖြစ်သည်။

---

### 6.8 IP Protocol Ping (-PO)

**Command:**
```
nmap -PO1,2,4 192.168.1.0/24
```

**Purpose:**
IP Protocol Header ကို ပို့၍ Host Discovery ပြုလုပ်သည်။ Protocol number 1=ICMP, 2=IGMP, 4=IP-in-IP စသည်ဖြင့်။

---

### 6.9 ARP Scan (-PR)

**Command:**
```
nmap -PR 192.168.1.0/24
```

**Purpose:**
Local Ethernet Network တွင် ARP Request ပို့၍ Host Discovery ပြုလုပ်သည်။

**Advantages:**
Local Network တွင် အလွန်မြန်ဆန်ပြီး အထိရောက်ဆုံးဖြစ်သည်။

> **Note:** Nmap သည် Local Network တွင် Auto-detection ဖြင့် ARP ကို အလိုအလျောက်သုံးသည်။ `--send-ip` ဖြင့် ARP အစား IP-level probes သုံးရန် အတင်းခိုင်းနိုင်သည်။

---

### 6.10 Skip Host Discovery (-Pn)

**Command:**
```
nmap -Pn 192.168.1.0/24
```

**Purpose:**
Host Discovery အဆင့်ကို ကျော်၍ Target အားလုံးကို Online ဟုယူဆပြီး Port Scan ကို တိုက်ရိုက်ဆက်လုပ်သည်။

**When to use:**
Host Discovery ကို ICMP/TCP/UDP အကုန် Block လုပ်ထားသော Highly Secured Network များတွင်။

**Performance consideration:**
`-Pn` ကို Subnet တစ်ခုလုံးတွင် အသုံးပြုပါက Dead Host များစွာကိုပါ Scan လုပ်မိသဖြင့် Scan Time သိသိသာသာကြာမြင့်နိုင်သည်။

---

### 6.11 Host Discovery Strategies — Comparative Table

| Method | Option | Protocol | Network | Speed | Stealth |
|--------|--------|----------|---------|-------|---------|
| ARP | `-PR` (auto) | ARP | Local LAN | Very Fast | Low |
| ICMP Echo | `-PE` | ICMP | Any | Fast | Low |
| TCP SYN Ping | `-PS` | TCP | Any | Fast | Medium |
| TCP ACK Ping | `-PA` | TCP | Any | Fast | High |
| UDP Ping | `-PU` | UDP | Any | Slow | Medium |
| Skip Discovery | `-Pn` | None | Any | Slow (many targets) | High |

**Recommended Combinations:**

```bash
# Internal LAN (no firewall)
nmap -sn 192.168.1.0/24

# External with firewall (most effective combination)
nmap -PE -PS443 -PA80 -PP 10.0.0.0/24

# Heavily filtered network
nmap -Pn -p 80,443 10.0.0.0/24
```

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 6.1: Host Discovery Lab**

```bash
# Exercise 1: Scan your local network (list scan first)
nmap -sL 192.168.1.0/24

# Exercise 2: Ping sweep your local network
nmap -sn 192.168.1.0/24

# Exercise 3: ARP scan
nmap -sn -PR 192.168.1.0/24

# Exercise 4: Compare results between -sn and -PE
nmap -sn 192.168.1.0/24 -oN ping_sweep.txt
nmap -PE 192.168.1.0/24 -oN icmp_echo.txt
diff ping_sweep.txt icmp_echo.txt

# Exercise 5: Check host discovery without ICMP
nmap -sn -PS80,443 --disable-arp-ping 8.8.8.8
```

---

### အကျဉ်းချုပ် (Summary)

- Host Discovery သည် Network အတွင်းရှိ Live Host များကို ရှာဖွေသည်
- Local Network တွင် ARP Scan သည် အမြန်ဆုံးနှင့် အထိရောက်ဆုံးဖြစ်သည်
- Firewall ရှေ့တွင် TCP SYN/ACK Ping သည် ICMP ထက် ပိုထိရောက်သည်
- `-Pn` သည် Host Discovery ကို Skip လုပ်၍ Target အားလုံးကို Online ဟု ယူဆသည်

### Key Takeaways

| Technique | Command | Best For |
|-----------|---------|----------|
| Ping Sweep | `-sn` | LAN, no firewall |
| TCP SYN Ping | `-PS` | Behind firewall |
| ICMP Echo | `-PE` | Simple, internal |
| Skip Discovery | `-Pn` | Heavily filtered |

---

## အခန်း ၇ — Port Scanning Techniques

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- TCP, UDP နှင့် Special Scan Type များအားလုံးကို ကျွမ်းကျင်မည်
- Scan Type တစ်ခုစီ၏ Internal Mechanism ကို နားလည်မည်
- အခြေအနေအလိုက် သင့်လျော်သော Scan Technique ကို ရွေးချယ်နိုင်မည်
- Scan Type များ၏ အကျိုး/အပြစ်များကို နှိုင်းယှဉ်နိုင်မည်

### ကြိုတင်လိုအပ်ချက်များ (Prerequisites)

- TCP/IP Headers နားလည်မှု (Chapter 2)
- Raw Socket သဘောတရား (Chapter 3)

---

### 7.1 TCP SYN (Stealth) Scan (-sS)

**Command:**
```
nmap -sS 192.168.1.1
```

**Syntax:** `-sS`

**How it works internally:**

```
Client (Nmap)                         Target Port X
     |                                      |
     |-------- SYN ------------------------>|  (1) Nmap sends SYN
     |                                      |
     |<------- SYN+ACK ---------------------|  (2a) If OPEN: Server responds SYN+ACK
     |                                      |
     |-------- RST ------------------------>|  (3a) Nmap sends RST (does NOT complete handshake)
     |                                      |
                    --- OR ---
     |                                      |
     |<------- RST -------------------------|  (2b) If CLOSED: Server responds RST
     |                                      |
```

**Response interpretation table:**

| Probe | Response | Assigned State |
|-------|----------|----------------|
| SYN | SYN/ACK | open |
| SYN | RST (reset) | closed |
| SYN | No response (after retransmissions) | filtered |
| SYN | ICMP unreachable error (type 3, code 1/2/3/9/10/13) | filtered |

**Advantages:**
- အမြန်ဆုံး TCP Scan — Connection မပြီးမီ RST ဖြင့်ဖြတ်သောကြောင့်
- Stealth — Application Log တွင် Connection အပြည့်အစုံပေါ်မည်မဟုတ်
- Open, Closed, Filtered States ကို ရှင်းရှင်းလင်းလင်း ခွဲခြားနိုင်

**Disadvantages:**
- root/sudo privileges လိုအပ် (Raw Socket)
- Modern IDS များက SYN Scan ကို သိရှိနိုင်

**Performance:**
Nmap သည် SYN Scan တွင် Congestion Control Algorithm ကို အသုံးပြုသည်။ Packet Loss ဖြစ်လျှင် Auto-throttle လုပ်သည်။

---

### 7.2 TCP Connect Scan (-sT)

**Command:**
```
nmap -sT 192.168.1.1
```

**Syntax:** `-sT`

**How it works internally:**
OS ၏ `connect()` system call ကို အသုံးပြု၍ TCP Three-Way Handshake အပြည့်အစုံ (SYN → SYN-ACK → ACK → RST) ကို Port တစ်ခုစီအတွက် ပြုလုပ်သည်။

**Advantages:**
- root privileges မလိုအပ်ပါ
- TCP Stack ၏ ပုံမှန်လုပ်ဆောင်ချက်ဖြစ်၍ Filter လုပ်ရန်ခက်ခဲ

**Disadvantages:**
- အလွန်နှေးကွေး — Connection တစ်ခုစီ အပြည့်အစုံတည်ဆောက်ရသောကြောင့်
- Noisy — Application Log တွင် Connection Record ပေါ်မည်
- Firewall/IDS များက အလွယ်တကူသိရှိနိုင်

**Security implications:**
Connect Scan သည် Application-level Logging ကို ဖြစ်ပေါ်စေသောကြောင့် Real-World Penetration Testing တွင် ရှောင်ကြဉ်သင့်သည်။

---

### 7.3 UDP Scan (-sU)

**Command:**
```
nmap -sU 192.168.1.1
```

**Syntax:** `-sU`

**How it works internally:**

```
Client (Nmap)                         Target Port X
     |                                      |
     |-------- UDP Probe ------------------>|  (1) Nmap sends UDP packet
     |                                      |
     |<------- UDP Response ----------------|  (2a) IF OPEN: App responds with UDP data
     |        (port = open)                 |
                    --- OR ---
     |                                      |
     |<------- ICMP Port Unreachable -------|  (2b) IF CLOSED: ICMP Type 3, Code 3
     |        (port = closed)               |
                    --- OR ---
     |                                      |
     |        (No Response)                 |  (2c) IF FILTERED: No response at all
     |        (port = open|filtered)        |
```

**Response interpretation table:**

| Probe | Response | Assigned State |
|-------|----------|----------------|
| UDP | Any UDP response | open |
| UDP | No response (retransmits done) | open\|filtered |
| UDP | ICMP port unreachable (type 3, code 3) | closed |
| UDP | Other ICMP unreachable (type 3, code 1/2/9/10/13) | filtered |

**Optimizing UDP Scans:**

```bash
# Scan common UDP ports only
nmap -sU -p 53,67,68,69,123,161,162,500,514,520,1900,5353

# Increase speed with more parallelism
nmap -sU --min-parallelism 100 --max-retries 2

# Use version detection to distinguish open|filtered
nmap -sU -sV -p 161 192.168.1.1
```

> **Performance consideration:** UDP Scan သည် TCP Scan ထက် အဆများစွာနှေးသည်။ Linux kernel သည် ICMP Port Unreachable ပို့မှုကို တစ်စက္ကန့်လျှင် ၁ ကြိမ်သာ ကန့်သတ်ထားသောကြောင့်ဖြစ်သည်။ `--max-retries` ကို 1 သို့မဟုတ် 2 သတ်မှတ်၍ အမြန်ဆုံးရရှိနိုင်သည်။

---

### 7.4 TCP FIN, NULL, Xmas Scans (-sF, -sN, -sX)

**Command:**
```
nmap -sF 192.168.1.1     # FIN Scan
nmap -sN 192.168.1.1     # NULL Scan
nmap -sX 192.168.1.1     # Xmas Scan
```

**Syntax:** `-sF`, `-sN`, `-sX`

**How it works internally:**

| Scan Type | Flags Sent | Open Port Response | Closed Port Response |
|-----------|-----------|-------------------|---------------------|
| FIN (-sF) | FIN only | **No Response** | RST |
| NULL (-sN) | None (0) | **No Response** | RST |
| Xmas (-sX) | FIN+PSH+URG | **No Response** | RST |

**Logic:** RFC 793 အရ Closed Port သို့ SYN မပါသော Packet ရောက်ပါက RST ပြန်ပို့ရမည်။ Open Port သို့ ရောက်ပါက Ignore လုပ်ရမည် (No Response)။ ထို့ကြောင့် Response မရှိလျှင် Open၊ RST ရလျှင် Closed ဟု ဆုံးဖြတ်သည်။

> **Warning:** Windows, BSD, Solaris အပါအဝင် OS အများစုသည် ဤ RFC Rule ကို အတိအကျမလိုက်နာပါ။ ထို Target များတွင် Port အားလုံး Closed ဟု ပြသနိုင်သည်။ Linux နှင့် Unix-based System များတွင်သာ ယုံကြည်စိတ်ချရသည်။

**Advantages:**
- Firewall/IDS အချို့ကို ကျော်လွှားနိုင်သည်
- SYN Scan ထက် Stealth ပိုကောင်းနိုင်သည်

---

### 7.5 TCP ACK Scan (-sA)

**Command:**
```
nmap -sA 192.168.1.1
```

**Syntax:** `-sA`

**How it works internally:**
ACK Packet ကို Random Sequence Number ဖြင့် Port သို့ပို့သည်။ Response ရရှိမှုပေါ်မူတည်၍:
- **RST Response:** Port unfiltered (open or closed — but reachable)
- **No Response / ICMP Error:** Port filtered (firewall blocking)

**Purpose:** Port State (open/closed) မဟုတ်ပဲ **Firewall Rules** ကို Map လုပ်ရန်။ ACK Scan ကို Firewall Detection အတွက်သာ အသုံးပြုသည်၊ Port Enumeration အတွက် မဟုတ်ပါ။

**When to use:**
Firewall Configuration ကို စစ်ဆေးလိုသည့်အခါ။ SYN Scan နှင့် ပေါင်းစပ်၍ အသုံးပြုလေ့ရှိသည်။

---

### 7.6 TCP Window Scan (-sW)

**Command:**
```
nmap -sW 192.168.1.1
```

**Syntax:** `-sW`

**How it works internally:**
ACK Scan ကဲ့သို့ ACK Packet ပို့သော်လည်း RST Packet ၏ TCP Window Field ကို စစ်ဆေးသည်။ အချို့ OS များတွင် Open Port အတွက် Window Size က Positive နှင့် Closed Port အတွက် Zero ဖြစ်တတ်သည်။

> **Limitation:** OS အများစုတွင် ယုံကြည်စိတ်ချရမှုမရှိပါ။ Few Systems အတွက်သာ အလုပ်လုပ်သည်။

---

### 7.7 TCP Maimon Scan (-sM)

**Command:**
```
nmap -sM 192.168.1.1
```

**Syntax:** `-sM`

**How it works internally:**
FIN+ACK Flags ပါသော Packet ကို ပို့သည်။ Uriel Maimon မှရှာဖွေတွေ့ရှိခဲ့သည့် နည်းလမ်းဖြစ်ပြီး BSD-derived Systems အများစုတွင် Open Port သည် Response မပြန်ပဲ Drop လုပ်တတ်သည်။

> **Note:** Windows, Linux, Solaris အပါအဝင် Modern OS အများစုတွင် အလုပ်မလုပ်တော့ပါ။

---

### 7.8 TCP Idle Scan (-sI)

**Command:**
```
nmap -sI zombie_host:port 192.168.1.1
```

**Syntax:** `-sI <zombie_host[:probe_port]>`

**How it works internally — Step by Step:**

```
Step 1: Probe Zombie's IP ID
  Nmap ----- SYN+ACK -----> Zombie (port X)
  Nmap <---- RST (IP ID=Y) -- Zombie

Step 2: Spoof packet to target from zombie
  Nmap [spoofing as Zombie] ----- SYN -----> Target (port Z)

Step 3: Probe Zombie's IP ID again
  Nmap ----- SYN+ACK -----> Zombie (port X)
  Nmap <---- RST (IP ID=Y+2) -- Zombie  --> Target OPEN
  OR
  Nmap <---- RST (IP ID=Y+1) -- Zombie  --> Target CLOSED
```

**Logic:** Target ထံမှ Zombie သို့ RST ပြန်လာပါက Zombie ၏ IP ID သည် 1 တိုးမည်။ Target Open ဖြစ်၍ SYN+ACK ပြန်လာပါက Zombie က RST ပြန်ပို့သဖြင့် IP ID 2 တိုးမည်။

**Zombie Host Requirements:**
- Idle (traffic မရှိသော) Host
- Predictable IP ID Sequence (Incremental)
- Reachable from both Nmap and Target

**Finding a Zombie:**
```bash
# Test if host has incremental IP ID
nmap -O -v zombie_candidate
# Look for: "IP ID Sequence Generation: Incremental"
```

**Advantages:**
- Completely Blind Scan — Nmap ၏ IP ကို Target မသိနိုင်
- Firewall Bypass အတွက် အသုံးဝင်

**Security implications:**
Idle Scan သည် အလွန်အဆင့်မြင့်သော Stealth Technique ဖြစ်သည်။ Target Log တွင် Zombie Host ၏ IP သာ ပေါ်မည်။

---

### 7.9 IP Protocol Scan (-sO)

**Command:**
```
nmap -sO 192.168.1.1
```

**Syntax:** `-sO`

**Purpose:** Target တွင် မည်သည့် IP Protocols (TCP=6, UDP=17, ICMP=1, IGMP=2, etc.) ကို Support လုပ်သည်ကို ရှာဖွေသည်။

**How it works internally:**
IP Protocol Header ကို Raw Packet အဖြစ်ပို့သည်။ Response ရရှိမှုပေါ်မူတည်၍ Protocol State ကို သတ်မှတ်သည်။

---

### 7.10 FTP Bounce Scan (-b)

**Command:**
```
nmap -b ftp_user:ftp_pass@ftp_server:21 192.168.1.1
```

**Syntax:** `-b <ftp relay host>`

**How it works internally:**
FTP Server ၏ PORT command ကို Proxy အဖြစ် အသုံးချ၍ Target ကို Scan ပြုလုပ်သည်။ FTP Server က Target Port သို့ Data Connection ဖွင့်နိုင်မှုကို စစ်ဆေးသည်။

> **Warning:** Modern FTP Servers အများစုသည် PORT command abuse ကို တားဆီးထားပြီးဖြစ်၍ ဤ Scan သည် ယနေ့ခေတ်တွင် အလုပ်လုပ်ခဲသည်။

---

### 7.11 Custom Scan Types (--scanflags)

**Command:**
```
nmap --scanflags SYNACKRST 192.168.1.1
nmap --scanflags URGACKPSHRSTSYNFIN 192.168.1.1   # All flags
nmap --scanflags PSH 192.168.1.1                    # PSH scan
```

**Syntax:** `--scanflags <flags>`

**Purpose:** မိမိစိတ်ကြိုက် TCP Flag Combination ဖြင့် Custom Scan ပြုလုပ်ရန်။ Flags များကို URG, ACK, PSH, RST, SYN, FIN မှ ပေါင်းစပ်နိုင်သည်။

> **Note:** Custom Scan သည် `-sS`, `-sF` စသည့် Standard Scan ၏ Behavior ကို Override လုပ်သည်။ Response Interpretation သည် သုံးထားသော Flags ပေါ်မူတည်သည်။

---

### 7.12 Complete Scan Types Comparison Table

| Scan | Option | Flags | Open | Closed | Filtered | Root | Speed | Stealth |
|------|--------|-------|------|--------|----------|------|-------|---------|
| SYN | `-sS` | SYN | SYN+ACK | RST | No Resp/ICMP | Yes | Fast | Medium |
| Connect | `-sT` | SYN→CONNECT | Full 3WHS | RST | Timeout | No | Slow | Low |
| UDP | `-sU` | UDP | UDP Resp/No Resp | ICMP Unreach | No Resp | Yes | Very Slow | Medium |
| FIN | `-sF` | FIN | No Response | RST | No Resp | Yes | Fast | High |
| NULL | `-sN` | None | No Response | RST | No Resp | Yes | Fast | High |
| Xmas | `-sX` | FIN+PSH+URG | No Response | RST | No Resp | Yes | Fast | High |
| ACK | `-sA` | ACK | RST (unfiltered) | RST (unfiltered) | No Resp/ICMP | Yes | Fast | High |
| Window | `-sW` | ACK | RST (win>0) | RST (win=0) | No Resp | Yes | Fast | Medium |
| Maimon | `-sM` | FIN+ACK | No Response | RST | No Resp | Yes | Fast | High |
| Idle | `-sI` | SYN (spoofed) | SYN+ACK (to zombie) | RST (to zombie) | — | Yes | Slow | Very High |
| IP Proto | `-sO` | IP Hdr | Response | No Resp | — | Yes | Medium | Low |
| FTP Bounce | `-b` | via FTP | Connect OK | Error | — | No | Slow | High |

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 7.1: Port Scanning Techniques Lab**

```bash
# Exercise 1: Default SYN scan
sudo nmap -sS scanme.nmap.org

# Exercise 2: Compare SYN vs Connect
sudo nmap -sS -p 22,80,443 scanme.nmap.org -oN syn_results.txt
nmap -sT -p 22,80,443 scanme.nmap.org -oN connect_results.txt

# Exercise 3: UDP scan on key ports
sudo nmap -sU -p 53,123,161 scanme.nmap.org

# Exercise 4: FIN scan
sudo nmap -sF scanme.nmap.org

# Exercise 5: ACK scan to map firewall
sudo nmap -sA scanme.nmap.org

# Exercise 6: Custom flag scan
sudo nmap --scanflags SYNFIN -p 80 scanme.nmap.org
sudo nmap --scanflags SYNACKRST -p 443 scanme.nmap.org
```

---

### အကျဉ်းချုပ် (Summary)

- SYN Scan (-sS) သည် အကောင်းဆုံး Default Scan ဖြစ်သည်
- Connect Scan (-sT) သည် root မလိုသော်လည်း နှေးပြီး Noisy ဖြစ်သည်
- UDP Scan (-sU) သည် အလွန်နှေးသော်လည်း UDP Services ရှာရန် မရှိမဖြစ်
- FIN/NULL/Xmas Scans သည် Windows တွင် အလုပ်မလုပ်ပါ
- Idle Scan (-sI) သည် Complete Anonymity ရရှိနိုင်သည်

### Key Takeaways

| Goal | Recommended Scan |
|------|-----------------|
| Default/Best | `-sS` (SYN) |
| Firewall Rules | `-sA` (ACK) |
| UDP Services | `-sU` |
| Total Stealth | `-sI` (Idle) |
| Custom Testing | `--scanflags` |

---

## အခန်း ၈ — Service & Version Detection

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Service Version Detection ၏ Internal Mechanism ကို နားလည်မည်
- Version Detection Intensity ကို ထိန်းချုပ်နိုင်မည်
- Banner Grabbing Technique ကို ကျွမ်းကျင်မည်
- SSL/TLS Service Analysis ကို လုပ်ဆောင်နိုင်မည်

---

### 8.1 Version Detection နိဒါန်း

Port Scanning သည် Port တစ်ခု Open ဖြစ်ကြောင်းသာ ပြသနိုင်သည်။ သို့သော် ထို Port တွင် **မည်သည့် Service** (Application) လည်ပတ်နေသည်၊ **မည်သည့် Version** ဖြစ်သည် ကို သိရှိရန် Version Detection လိုအပ်သည်။

**Version Detection လုပ်နိုင်သည်များ:**
- Service Name (e.g., Apache httpd, OpenSSH, MySQL)
- Version Number (e.g., 2.4.7, 7.4p1, 8.0.28)
- Operating System (of the service host)
- Device Type
- Additional Info (protocol version, etc.)

---

### 8.2 -sV Option

**Command:**
```
nmap -sV 192.168.1.1
```

**Syntax:** `-sV [--version-intensity <0-9>] [--version-light | --version-all]`

**How it works internally:**

Nmap Version Detection သည် `nmap-service-probes` Database ကို အသုံးပြုသည်။ အောက်ပါ Steps များကို လုပ်ဆောင်သည်:

1. **Service Probe ပို့ခြင်း:** Open Port တစ်ခုစီသို့ Predefined Probe အတွဲများ ပို့သည်
2. **Response Capture:** Service ၏ တုံ့ပြန်မှုကို ဖမ်းယူသည်
3. **Pattern Matching:** Response ကို Database ရှိ Regular Expression Patterns များနှင့် တိုက်ကြည့်သည်
4. **Cheats & Fallbacks:** Port number lookup, SSL detection, RPC grinding တို့နှင့် ပေါင်းစပ်သည်
5. **Result Classification:** Match အများဆုံးဖြစ်သော Service Name နှင့် Version ကို ပြသသည်

**Probe Selection & Rarity:**
Database ရှိ Probe များကို Rarity 1 (common) မှ 9 (rare) အထိ ခွဲခြားထားသည်။ Intensity Level ပေါ်မူတည်၍ Probe အရေအတွက် ကွာခြားသည်။

---

### 8.3 Version Detection Intensity

| Option | Intensity | Probes | Speed | Accuracy |
|--------|-----------|--------|-------|----------|
| `--version-light` | 2 | Few probes (rarity ≤2) | Fast | Lower |
| `-sV` (default) | 7 | Most probes (rarity ≤7) | Moderate | High |
| `--version-all` | 9 | All probes (rarity ≤9) | Slow | Maximum |

**Command examples:**

```
nmap -sV --version-light 192.168.1.1   # Light, fast
nmap -sV 192.168.1.1                    # Default (intensity 7)
nmap -sV --version-all 192.168.1.1     # All probes
nmap -sV --version-intensity 5 192.168.1.1   # Custom intensity
```

**When to use each:**
- `--version-light`: Quick scan, many targets
- default `-sV`: Normal penetration testing
- `--version-all`: Deep investigation of specific host

---

### 8.4 Banner Grabbing

Service Banner သည် Service နှင့် Connect လုပ်သည့်အခါ Service မှ အလိုအလျောက် ပြန်ပို့သော Greeting Message ဖြစ်သည်။

**Nmap ဖြင့် Banner Grabbing:**

```bash
nmap -sV -p 22 192.168.1.1
# Shows: 22/tcp open  ssh     OpenSSH 7.4 (protocol 2.0)

nmap -sV -p 80 192.168.1.1
# Shows: 80/tcp open  http    Apache httpd 2.4.7 ((Ubuntu))

nmap -sV -p 3306 192.168.1.1
# Shows: 3306/tcp open  mysql  MySQL 5.7.33
```

**Sample output:**

```
PORT     STATE SERVICE  VERSION
22/tcp   open  ssh      OpenSSH 5.3p1 Debian 3ubuntu7 (protocol 2.0)
80/tcp   open  http     Apache httpd 2.2.14 ((Ubuntu))
3306/tcp open  mysql    MySQL 5.5.62
```

**Output explanation:**
- `PORT`: Port number နှင့် protocol
- `STATE`: Port State (open)
- `SERVICE`: Service name (ssh, http, mysql)
- `VERSION`: Version အသေးစိတ် (vendor, version, OS if available)

---

### 8.5 RPC Grinding

SunRPC (Remote Procedure Call) Service များသည် Dynamic Port တွင် Run လေ့ရှိပြီး Portmapper (port 111) တွင် Register လုပ်ထားသည်။

Nmap သည် RPC Grinding ဖြင့်:
- TCP/UDP Port 111 ရှိ Portmapper ကို Query လုပ်၍ Dynamic RPC Service များ၏ Port ကို ရှာဖွေသည်
- RPC Program Number မှ Service Name သို့ `nmap-rpc` File ကို အသုံးပြု၍ ဘာသာပြန်သည်

---

### 8.6 SSL/TLS Analysis

Nmap သည် SSL/TLS Encrypted Service များအတွက် OpenSSL ကို အသုံးပြု၍ Encryption Layer ကို Unwrap လုပ်နိုင်သည်။

**SSL Post-processor:**
- HTTPS (443), SMTPS (465), IMAPS (993), POP3S (995) စသည့် SSL Services များပေါ်တွင် Version Detection လုပ်နိုင်ရန်
- SSL Certificate Analysis — certificate issuer, validity, subject

**Command:**
```
nmap -sV --script=ssl-enum-ciphers -p 443 192.168.1.1
```

---

### 8.7 nmap-service-probes Database

Nmap ၏ Version Detection Engine သည် `/usr/share/nmap/nmap-service-probes` File ကို အသုံးပြုသည်။ ဤ File တွင်:

- **Exclude Directive:** Scan မလုပ်သင့်သော Port များ
- **Probe Directive:** Probe definition (protocol, payload, ports)
- **match Directive:** Response matching rule (pattern, version info)
- **softmatch Directive:** Secondary matching for indirect identification
- **rarity Directive:** Probe အသုံးပြုရန် အနည်းဆုံး intensity level

**Community Contribution:**
- မိမိတွေ့ရှိသော Service Fingerprint များကို Nmap Project သို့ Submit လုပ်နိုင်သည်
- `-sV --version-all` ဖြင့် Unknown Service များကို ရှာဖွေနိုင်သည်

---

### Version Detection Optimization

```bash
# Quick version scan (top ports)
nmap -sV --version-light -F 192.168.1.0/24

# Deep scan on specific port
nmap -sV --version-all -p 8443 192.168.1.1

# Custom intensity on critical hosts
nmap -sV --version-intensity 8 -p 1-1000 192.168.1.1

# Combined with OS detection and scripts
nmap -sV -O -sC -p 22,80,443 192.168.1.1
```

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 8.1: Version Detection Lab**

```bash
# Exercise 1: Basic version detection
nmap -sV scanme.nmap.org

# Exercise 2: Light vs All comparison
nmap -sV --version-light scanme.nmap.org -oN light.txt
nmap -sV --version-all scanme.nmap.org -oN full.txt

# Exercise 3: Scan specific services
nmap -sV -p 21,22,25,80,443,3306 192.168.1.1

# Exercise 4: Version + OS + Scripts combo
sudo nmap -sV -O -sC 192.168.1.1
```

---

### အကျဉ်းချုပ် (Summary)

- Version Detection သည် Open Port တွင် လည်ပတ်နေသော Service ၏ Name နှင့် Version ကို ဖော်ထုတ်သည်
- `nmap-service-probes` Database တွင် Probe များနှင့် Match Rules များ ပါဝင်သည်
- Intensity Level (0-9) ဖြင့် Speed vs Accuracy Balance ပြုလုပ်နိုင်သည်
- SSL/TLS Services အတွက် OpenSSL ကို အသုံးပြု၍ Decrypt လုပ်နိုင်သည်

### Key Takeaways

| Option | Intensity | Use Case |
|--------|-----------|----------|
| `--version-light` | 2 | Quick scan |
| `-sV` (default) | 7 | Normal scan |
| `--version-all` | 9 | Deep investigation |

---

## အခန်း ၉ — OS Detection (Operating System Detection)

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- TCP/IP Fingerprinting ၏ သဘောတရားကို နားလည်မည်
- OS Detection Options များကို ကျွမ်းကျင်မည်
- OS Detection Accuracy ကို မြှင့်တင်နိုင်မည်
- Unidentified Host များအတွက် Fingerprint Submit လုပ်နိုင်မည်

---

### 9.1 OS Detection နိဒါန်း

Remote OS Detection ဆိုသည်မှာ Target Host ၏ Operating System (OS) နှင့် Version ကို Network Traffic မှတစ်ဆင့် ဖော်ထုတ်ခြင်းဖြစ်သည်။

**OS Detection လိုအပ်သော အကြောင်းများ:**

| Reason | Description |
|--------|-------------|
| Vulnerability Assessment | OS-Specific Vulnerabilities ရှာဖွေခြင်း |
| Exploit Tailoring | OS နှင့် ကိုက်ညီသော Exploit ရွေးချယ်ခြင်း |
| Network Inventory | Network အတွင်းရှိ OS များကို စာရင်းပြုစုခြင်း |
| Unauthorized Devices | ခွင့်ပြုချက်မရှိသော Device များရှာဖွေခြင်း |
| Social Engineering | Target အဖွဲ့အစည်း၏ IT Infrastructure အချက်အလက် |

---

### 9.2 -O Option

**Command:**
```
nmap -O 192.168.1.1
```

**Syntax:** `-O [--osscan-limit] [--osscan-guess] [--max-os-tries N]`

**How it works internally:**

Nmap OS Detection သည် **TCP/IP Stack Fingerprinting** Technique ကို အသုံးပြုသည်။ OS တစ်ခုနှင့်တစ်ခု TCP/IP Stack Implementation တွင် ကွဲပြားချက်များရှိပြီး ထိုကွဲပြားချက်များကို "Fingerprint" အဖြစ် စုဆောင်းသည်။

**Probes Sent (IPv4):**

| Probe | Type | Purpose |
|-------|------|---------|
| Sequence (SEQ, OPS, WIN, T1) | TCP | TCP Sequence Generation, Options, Window Size |
| IE | ICMP Echo | ICMP Response patterns |
| ECN | TCP | Explicit Congestion Notification behavior |
| T2-T7 | TCP | Various TCP flag combinations |
| U1 | UDP | UDP Response behavior |

**Response Tests (16 categories):**

Nmap သည် Response များကို Test 16 မျိုးဖြင့် စစ်ဆေးသည်:

| Test | Full Name | What It Measures |
|------|-----------|-----------------|
| GCD | TCP ISN Greatest Common Divisor | Randomness of sequence numbers |
| ISR | TCP ISN Counter Rate | How fast sequence numbers increment |
| SP | Sequence Predictability Index | How predictable sequences are |
| TI/CI/II | IP ID Sequence Algorithm | IP ID generation method |
| TS | TCP Timestamp Option | Timestamp implementation |
| O/O1-O6 | TCP Options | Options support and ordering |
| W/W1-W6 | TCP Initial Window Size | Initial TCP window |
| R | Responsiveness | How responsive the target is |
| DF | Don't Fragment bit | DF flag behavior |
| T | Initial TTL | Initial Time to Live value |
| Q | TCP Quirks | Unusual TCP behaviors |
| S | Sequence Number | Sequence number handling |
| A | Acknowledgment Number | ACK number handling |
| F | Flags | TCP flag behavior |
| RD | RST Data Checksum | RST packet checksum |
| IPL | IP Total Length | IP packet length |

---

### 9.3 OS Detection Options

```bash
# Basic OS detection
nmap -O 192.168.1.1

# Limit to likely matches (only if at least one open, one closed port)
nmap -O --osscan-limit 192.168.1.1

# Guess OS aggressively (show near-matches too)
nmap -O --osscan-guess 192.168.1.1

# Maximum retries for host
nmap -O --max-os-tries 5 192.168.1.1

# Combined with version detection (recommended)
nmap -O -sV 192.168.1.1
```

**Sample output:**

```
Device type: general purpose
Running: Linux 2.6.X|3.X
OS CPE: cpe:/o:linux:linux_kernel:2.6.39
OS details: Linux 2.6.39
Network Distance: 11 hops
```

**Output explanation:**
- `Device type`: General purpose, router, switch, printer, WAP
- `Running`: OS family and version guess (with alternatives)
- `OS CPE`: Common Platform Enumeration identifier
- `OS details`: Most specific match
- `Network Distance`: Number of hops (from traceroute)

---

### 9.4 OS Detection Accuracy

**Accuracy မြှင့်တင်ရန်:**

```bash
# Ensure at least one open AND one closed TCP port
nmap -O -p 80 --osscan-guess 192.168.1.1

# Combine with version detection for cross-reference
nmap -O -sV 192.168.1.1

# Use IPv6 detection if available
nmap -6 -O 2001:db8::1
```

**When Nmap guesses wrong:**
1. Firewall/Packet Filtering ကြောင့်
2. OS Fingerprint Database (`nmap-os-db`) တွင် ထို OS Version အတိအကျမရှိခြင်း
3. Target OS က TCP/IP Stack ကို Customize လုပ်ထားခြင်း

**Unidentified Hosts:**
Nmap က Match မတွေ့ပါက Fingerprint ကို Print ထုတ်ပြသည်။ ထို Fingerprint ကို Nmap Project သို့ Submit လုပ်၍ Database တိုးတက်စေရန် ကူညီနိုင်သည်။

---

### 9.5 nmap-os-db Database

OS Fingerprint Database သည် `/usr/share/nmap/nmap-os-db` File တွင် ရှိသည်။

**Database ကို ကိုယ်တိုင်ပြင်ဆင်ခြင်း:**
- Reference Fingerprints များ၏ Format ကို နားလည်ပြီး ဖြည့်စွက်နိုင်သည်
- Free-form OS Description (`Fingerprint` line)
- Device Classification (`Class` lines)
- Test Expressions (Lua-based matching logic)

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 9.1: OS Detection Lab**

```bash
# Exercise 1: Basic OS detection
sudo nmap -O scanme.nmap.org

# Exercise 2: Aggressive OS detection
sudo nmap -O --osscan-guess scanme.nmap.org

# Exercise 3: Combined OS + Version
sudo nmap -O -sV scanme.nmap.org

# Exercise 4: Compare limited vs full
sudo nmap -O --osscan-limit 192.168.1.1
sudo nmap -O 192.168.1.1
```

---

### အကျဉ်းချုပ် (Summary)

- Nmap OS Detection သည် TCP/IP Stack Fingerprinting ကို အသုံးပြုသည်
- Probes 10+ မျိုးကို ပို့၍ 16 Test Categories ဖြင့် ခွဲခြမ်းစိတ်ဖြာသည်
- Accuracy အတွက် Open Port နှင့် Closed Port နှစ်မျိုးလုံးရှိရန် လိုအပ်သည်
- `--osscan-guess` ဖြင့် Near-matches ပါ ကြည့်နိုင်သည်

### Key Takeaways

| Option | Purpose |
|--------|---------|
| `-O` | Basic OS detection |
| `--osscan-limit` | Only if ports exist |
| `--osscan-guess` | Aggressive guessing |
| `-O -sV` | Combined (recommended) |
| `nmap-os-db` | Fingerprint database |

---

---

## အပိုင်း ၃ — Advanced Techniques

---

## အခန်း ၁၀ — Nmap Scripting Engine (NSE)

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- NSE Architecture ကို နားလည်မည်
- Script Categories များကို ကျွမ်းကျင်မည်
- Script Selection နှင့် Arguments များကို အသုံးပြုနိုင်မည်
- Vulnerability Detection Scripts များကို လုပ်ဆောင်နိုင်မည်
- Custom Script Writing ၏ အခြေခံကို သိရှိမည်

---

### 10.1 NSE မိတ်ဆက်

**NSE (Nmap Scripting Engine)** သည် Nmap ၏ အစွမ်းထက်ဆုံး Feature ဖြစ်ပြီး Lua Programming Language ကို အခြေခံထားသည်။ NSE ဖြင့် အောက်ပါတို့ကို လုပ်ဆောင်နိုင်သည်:

- **Network Discovery** — WHOIS, DNS, SMB, LDAP
- **Version Detection** (Advanced) — Service-specific probes
- **Vulnerability Detection** — CVE lookup, known vulnerabilities
- **Backdoor Detection** — Malware backdoors
- **Exploitation** — Basic exploitation capabilities
- **Brute Force** — Password auditing

**NSE Development History:**
- Nmap 5.0 (2009) တွင် ပထမဆုံးမိတ်ဆက်
- Nmap 6.0 တွင် Script 300+
- Nmap 7.90 တွင် Script 600+

---

### 10.2 Script Architecture

**Script Locations:**

```bash
# System scripts
/usr/share/nmap/scripts/

# User scripts
~/.nmap/scripts/

# Script database
/usr/share/nmap/scripts/script.db

# Update script database
nmap --script-updatedb
```

**Script ရှာဖွေခြင်း:**

```bash
# List all scripts
ls /usr/share/nmap/scripts/

# Search by keyword
locate *.nse
locate *vuln*.nse
locate *http*.nse | head -20

# Get script info
nmap --script-help http-title
nmap --script-help "smb-*"
```

---

### 10.3 Script Categories

NSE Scripts များကို Category များဖြင့် အုပ်စုခွဲထားသည်:

| Category | Description | Example Scripts |
|----------|-------------|-----------------|
| `safe` | Target ကို အန္တရာယ်မပြုသော Scripts | http-title, ssh-hostkey |
| `default` | Default safe scripts (`-sC` နှင့် ညီမျှ) | (many) |
| `discovery` | Network information gathering | dns-brute, snmp-info |
| `version` | Version detection enhancement | (used with -sV) |
| `vuln` | Vulnerability detection | smb-vuln-ms17-010 |
| `auth` | Authentication bypass/check | http-auth, ftp-anon |
| `broadcast` | Network-wide broadcast | broadcast-dns-service-discovery |
| `brute` | Brute force credential testing | http-brute, ftp-brute |
| `dos` | Denial of Service testing | (potentially harmful) |
| `exploit` | Active exploitation | (use with caution) |
| `external` | External service interaction | ip-geolocation-*, whois-* |
| `fuzzer` | Fuzz testing | dns-fuzz |
| `intrusive` | Intrusive (might crash target) | http-slowloris |
| `malware` | Malware detection | http-google-malware |

---

### 10.4 Script Types & Phases

Scripts များကို Execution Phase အလိုက် အမျိုးအစား (၄) မျိုး ခွဲခြားထားသည်:

| Phase | Type | When It Runs |
|-------|------|-------------|
| **prerule** | Pre-scanning | Scan မစတင်မီ (e.g., target resolution) |
| **hostrule** | Host scripts | Host တစ်ခုစီအတွက် OS detection ပြီးနောက် |
| **portrule** | Service scripts | Port တစ်ခုစီအတွက် service detection ပြီးနောက် |
| **postrule** | Post-scanning | Scan အားလုံးပြီးနောက် (e.g., summary, reporting) |

---

### 10.5 Script Selection

**Command:**
```
nmap --script <script-spec> [target]
```

**Script Selection Methods:**

```bash
# Single script
nmap --script http-title 192.168.1.1

# Multiple scripts
nmap --script http-title,ssl-enum-ciphers 192.168.1.1

# By category
nmap --script default 192.168.1.1        # same as -sC
nmap --script safe 192.168.1.1           # safe category
nmap --script vuln 192.168.1.1           # vulnerability category
nmap --script "default and safe" 192.168.1.1

# Wildcard selection
nmap --script "http-*" 192.168.1.1
nmap --script "smb-*" 192.168.1.0/24

# By directory
nmap --script /path/to/custom/scripts 192.168.1.1

# Excluding scripts
nmap --script "not intrusive" 192.168.1.1
nmap --script "default and not http-*" 192.168.1.1

# Boolean expressions
nmap --script "(http-* or ssl-*) and not (brute or dos)" 192.168.1.1
```

---

### 10.6 Script Arguments

**Syntax:**
```
nmap --script <script> --script-args <args>
nmap --script <script> --script-args=<args>
```

**Examples:**

```bash
# Single argument
nmap --script http-title --script-args http.title.url=/login 192.168.1.1

# Multiple arguments
nmap --script http-brute --script-args 'userdb=users.txt,passdb=pass.txt'

# From file
nmap --script http-brute --script-args-file args.txt

# Specific script arguments
nmap --script smb-enum-shares --script-args smbusername=admin,smbpassword=admin 192.168.1.1
```

---

### 10.7 Key NSE Scripts by Service

#### HTTP Scripts

```bash
# Basic enumeration
nmap --script http-title,http-headers -p 80,443 192.168.1.1

# Hidden files/directories
nmap --script http-enum -p 80,443 192.168.1.1

# HTTP methods check
nmap --script http-methods -p 80,443 192.168.1.1

# WAF detection
nmap --script http-waf-detect -p 80,443 www.example.com
nmap --script http-waf-fingerprint -p 80,443 www.example.com

# Vulnerability
nmap --script http-shellshock --script-args uri=/cgi-bin/test.cgi 192.168.1.1
nmap --script http-slowloris 192.168.1.1
```

---

#### SMB Scripts

```bash
# Enumeration
nmap --script smb-os-discovery -p 445 192.168.1.0/24
nmap --script smb-enum-shares,smb-enum-users -p 445 192.168.1.1

# Vulnerability scanning
nmap --script smb-vuln-ms17-010 -p 445 192.168.1.0/24
nmap --script smb-vuln-ms08-067 -p 445 192.168.1.0/24
nmap --script smb-vuln-* -p 445 192.168.1.1

# Brute force
nmap --script smb-brute -p 445 192.168.1.1
```

---

#### DNS Scripts

```bash
# DNS enumeration
nmap --script dns-brute -p 53 domain.com
nmap --script dns-zone-transfer -p 53 --script-args dns-zone-transfer.server=ns1.domain.com domain.com
nmap --script dns-recursion -p 53 8.8.8.8
```

---

#### SSL/TLS Scripts

```bash
# Cipher enumeration
nmap --script ssl-enum-ciphers -p 443 192.168.1.1

# Certificate analysis
nmap --script ssl-cert -p 443 192.168.1.1

# Vulnerability check
nmap --script ssl-heartbleed -p 443 192.168.1.1
nmap --script ssl-poodle -p 443 192.168.1.1
nmap --script ssl-ccs-injection -p 443 192.168.1.1
```

---

#### Database Scripts

```bash
# MySQL
nmap --script mysql-enum -p 3306 192.168.1.1
nmap --script mysql-brute -p 3306 192.168.1.1
nmap --script mysql-empty-password -p 3306 192.168.1.1
nmap --script mysql-info -p 3306 192.168.1.1

# PostgreSQL
nmap --script pgsql-brute -p 5432 192.168.1.1

# MSSQL
nmap --script ms-sql-info -p 1433 192.168.1.1
```

---

#### FTP Scripts

```bash
# Anonymous login check
nmap --script ftp-anon -p 21 192.168.1.1

# FTP enumeration
nmap --script ftp-brute -p 21 192.168.1.1
nmap --script ftp-proftpd-backdoor -p 21 192.168.1.1
```

---

#### SSH Scripts

```bash
# Host key display
nmap --script ssh-hostkey -p 22 192.168.1.1

# Algorithms enumeration
nmap --script ssh2-enum-algos -p 22 192.168.1.1

# Auth methods
nmap --script ssh-auth-methods -p 22 192.168.1.1
```

---

#### SMTP Scripts

```bash
# Enumeration
nmap --script smtp-commands -p 25 192.168.1.1
nmap --script smtp-enum-users -p 25 192.168.1.1
nmap --script smtp-open-relay -p 25 192.168.1.1
```

---

### 10.8 Vulnerability Scripts in Detail

**EternalBlue (MS17-010):**

```bash
nmap -Pn -p445 --script=smb-vuln-ms17-010 192.168.1.0/24 -oN eternalblue-scan.txt
```

- SMB Port 445 တွင် EternalBlue Vulnerability ကို စစ်ဆေးသည်
- 2017 WannaCry Ransomware အတွက် အဓိက Exploit
- Result ကို Text File တွင် သိမ်းဆည်း

---

**Vulnerability Database (Vulners):**

```bash
# Step 1: Install (clone from git)
cd /usr/share/nmap/scripts/
git clone https://github.com/vulnersCom/nmap-vulners.git

# Step 2: Run
nmap -Pn -sV -p80 --script=vulners scanme.nmap.org
```

**Sample output:**
```
PORT   STATE SERVICE VERSION
80/tcp open  http    Apache httpd 2.4.7 ((Ubuntu))
| vulners:
|   cpe:/a:apache:http_server:2.4.7:
|       CVE-2017-7679  7.5  https://vulners.com/cve/CVE-2017-7679
|       CVE-2018-1312  6.8  https://vulners.com/cve/CVE-2018-1312
|       CVE-2014-0226  6.8  https://vulners.com/cve/CVE-2014-0226
|_      CVE-2017-9798  5.0  https://vulners.com/cve/CVE-2017-9798
```

---

**Geolocation:**

```bash
nmap --script=ip-geolocation-ipinfodb --script-args=ip-geolocation-ipinfodb.apikey=APIKEY 8.8.8.8
```

- IP Address ၏ Geographic Location ရှာဖွေခြင်း
- ipinfodb.com တွင် အခမဲ့ API Key ရယူရန်လိုအပ်

---

### 10.9 Writing Custom Scripts (အခြေခံ)

NSE Script ကို Lua Language ဖြင့် ရေးသားပြီး `.nse` Extension ဖြင့် သိမ်းဆည်းသည်။

**Basic Script Structure:**

```lua
-- My first NSE script
local stdnse = require "stdnse"
local shortport = require "shortport"

description = [[
A simple example script that displays HTTP title.
]]

author = "Your Name"
license = "Same as Nmap--See https://nmap.org/book/man-legal.html"
categories = {"default", "discovery", "safe"}

-- The rule: when to run
portrule = shortport.http

-- The action: what to do
action = function(host, port)
    return stdnse.format_output(true, "Hello from NSE!")
end
```

**Script တွင် အဓိက အစိတ်အပိုင်း (၃) ခု:**

1. **Head:** Description, author, license, categories
2. **Rule:** Script ကို မည်သည့်အခါ Run မည် (portrule, hostrule, prerule, postrule)
3. **Action:** အမှန်တကယ်လုပ်ဆောင်ရမည့်အလုပ်

**NSE Libraries (Built-in):**
- `stdnse` — Standard NSE utilities
- `shortport` — Port rule shortcuts
- `http` — HTTP library
- `smb` — SMB library
- `ssl` — SSL/TLS library
- `dns` — DNS library
- `nmap` — Nmap core API

---

### 10.10 Script Parallelism

NSE သည် Multi-threading ကို Support လုပ်သည်။ Script များကို Worker Threads ဖြင့် Parallel Run လုပ်နိုင်သည်။

- **Worker Threads:** Thread အရေအတွက်ကို `--min-parallelism` နှင့် `--max-parallelism` ဖြင့် ထိန်းချုပ်
- **Mutexes:** Thread-safe data access အတွက်
- **Condition Variables:** Thread synchronization
- **Collaborative Multithreading:** Lua coroutines based

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 10.1: NSE Scripts Lab**

```bash
# Exercise 1: Default scripts
nmap -sC scanme.nmap.org

# Exercise 2: HTTP discovery
nmap --script "http-*" -p 80,443 scanme.nmap.org

# Exercise 3: SSL analysis
nmap --script ssl-enum-ciphers,ssl-cert -p 443 scanme.nmap.org

# Exercise 4: Vulnerability check
nmap --script vuln scanme.nmap.org

# Exercise 5: List all safe scripts
nmap --script "safe" 192.168.1.1

# Exercise 6: Custom script selection
nmap --script "(http-* or smb-*) and safe" 192.168.1.0/24
```

---

### အကျဉ်းချုပ် (Summary)

- NSE သည် Lua-based Scripting Engine ဖြစ်ပြီး Nmap ၏ Functionality ကို တိုးချဲ့ပေးသည်
- Scripts များကို Category (14+) နှင့် Phase (4) ဖြင့် ခွဲခြားထားသည်
- Script 600+ ခုပါဝင်ပြီး Discovery, Vulnerability, Exploitation အထိ လုပ်ဆောင်နိုင်သည်
- Custom Script ကို Lua ဖြင့်ရေးသား၍ `.nse` အဖြစ်သိမ်းရုံဖြင့် အသုံးပြုနိုင်

### Key Takeaways

| Task | Command |
|------|---------|
| Default scripts | `nmap -sC` |
| All safe scripts | `nmap --script safe` |
| Vulnerability | `nmap --script vuln` |
| Help | `nmap --script-help <name>` |
| Update DB | `nmap --script-updatedb` |

---

## အခန်း ၁၁ — Timing & Performance Optimization

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Timing Templates များ၏ ကွာခြားချက်ကို နားလည်မည်
- Low-Level Timing Controls များကို ကျွမ်းကျင်မည်
- Performance Optimization Techniques များကို သိရှိမည်
- Long Scan များအတွက် နည်းဗျူဟာများကို ရေးဆွဲနိုင်မည်

---

### 11.1 Timing Templates (-T0 to -T5)

**Command:**
```
nmap -T4 192.168.1.1
```

**Syntax:** `-T<0-5>`

Timing Templates များသည် Nmap ၏ Low-Level Timing Parameters များကို Pre-configured Set အဖြစ် စုစည်းပေးထားသည်။

| Template | Name | Characteristics |
|----------|------|----------------|
| **-T0** | Paranoid | Serialized scan, 5-minute wait between probes. IDS evasion extreme |
| **-T1** | Sneaky | Serialized scan, 15-second wait. IDS evasion moderate |
| **-T2** | Polite | Slower than normal (~10x slower than T3). Bandwidth-friendly |
| **-T3** | Normal | Default. Parallel, reasonable timing |
| **-T4** | Aggressive | Fast, assumes good network. 10ms max scan delay |
| **-T5** | Insane | Maximum speed. 5ms scan delay, may miss ports |

**Each Template Sets:**

| Parameter | T0 | T1 | T2 | T3 | T4 | T5 |
|-----------|----|----|----|----|----|-----|
| min-rtt-timeout | 100ms | 100ms | 100ms | 100ms | 100ms | 50ms |
| max-rtt-timeout | 5min | 15s | 10s | 10s | 1250ms | 300ms |
| initial-rtt-timeout | 5min | 15s | 1s | 1s | 500ms | 250ms |
| max-retries | 10 | 10 | 10 | 10 | 6 | 2 |
| scan-delay | 5min | 15s | 400ms | 0 | 0-10ms | 0-5ms |
| max-scan-delay | 5min | 15s | 1s | 1s | 10ms | 5ms |
| max-parallelism | 1 | 1 | 1 | 0 | 0 | 0 |
| min-parallelism | 1 | 1 | 1 | 0 | 0 | 0 |

**When to use each:**

| Template | Use Case |
|----------|----------|
| T0 | Extreme stealth required. You have days to wait |
| T1 | Stealth needed. You have hours |
| T2 | Low bandwidth, polite to target |
| T3 | Default — good balance |
| T4 | Most real engagements. Fast, reliable |
| T5 | High-speed internal network. May miss ports |

> **Common Mistake:** T5 ကို Remote Network တွင် အသုံးပြုပါက Packet Loss များပြား၍ Port များ Miss ဖြစ်နိုင်သည်။ T4 သည် ယေဘုယျအားဖြင့် အကောင်းဆုံး Balance ဖြစ်သည်။

---

### 11.2 Low-Level Timing Controls

```bash
# Host timing
nmap --min-hostgroup 256 --max-hostgroup 1024
nmap --min-parallelism 100 --max-parallelism 200

# Probe timing
nmap --min-rtt-timeout 50ms --max-rtt-timeout 500ms --initial-rtt-timeout 200ms

# Retry control
nmap --max-retries 3

# Rate limiting
nmap --min-rate 100 --max-rate 500

# Scan delay (stealth)
nmap --scan-delay 1s --max-scan-delay 5s

# Host timeout
nmap --host-timeout 30m

# For defeating rate-limit (e.g. Linux ICMP limit)
nmap --defeat-rst-ratelimit
nmap --defeat-icmp-ratelimit
```

**Key Parameters Explained:**

| Parameter | Description | Effect |
|-----------|-------------|--------|
| `--min-hostgroup` | Minimum hosts to scan in parallel | Higher = faster for many targets |
| `--max-parallelism` | Max concurrent probes | Higher = faster but noisier |
| `--min-rtt-timeout` | Minimum round-trip timeout | Lower = faster on fast networks |
| `--max-rtt-timeout` | Maximum timeout before giving up | Lower = less waiting |
| `--max-retries` | Max probe retransmissions | Lower = faster, may miss ports |
| `--scan-delay` | Delay between probes | Higher = stealthier, slower |
| `--max-rate` | Max packets per second | Bandwidth-friendly |
| `--host-timeout` | Max time per host | Prevents hanging on dead hosts |
| `--defeat-rst-ratelimit` | Bypass RST rate limiting | Improves accuracy on Linux targets |

---

### 11.3 Performance Optimization Strategies

**Strategy 1: Multi-stage Scanning**

```bash
# Stage 1: Fast host discovery
nmap -sn -T4 10.0.0.0/24 -oA stage1_discovery

# Stage 2: Extract live hosts
awk '/Up$/{print $2}' stage1_discovery.gnmap > livehosts.txt

# Stage 3: Top ports on live hosts only
nmap -sS -sV --top-ports 100 -T4 -iL livehosts.txt -oA stage2_top

# Stage 4: Full port scan on specific hosts (optional)
nmap -sS -sV -p- -T4 -iL critical_hosts.txt -oA stage3_full
```

**Strategy 2: Separate UDP Scans**

```bash
# TCP scan (fast)
nmap -sS -sV -T4 -oA tcp_scan 192.168.1.0/24

# UDP scan (separate, limited ports)
nmap -sU -sV -p 53,123,161,500,1900 -T4 -oA udp_scan 192.168.1.0/24
```

**Strategy 3: Omit Non-critical Tests**

```bash
# Skip DNS resolution for speed
nmap -n -sS -T4 192.168.1.0/24

# Skip host discovery if all hosts are known alive
nmap -Pn -sS -T4 -iL livehosts.txt

# Skip reverse DNS
nmap -n -sS 192.168.1.0/24
```

**Strategy 4: Scan from Favorable Location**

- Target နှင့် Network ပိုင်းအရ နီးစပ်သောနေရာမှ Scan ပြုလုပ်ပါ
- High bandwidth, low latency connection ဖြင့်သုံးပါ
- Concurrent Nmap Instances ခွဲ၍ Scan လုပ်နိုင်သည် (e.g., subnet ကို တစ်ဝက်စီ)

---

### 11.4 Scan Time Estimation

Scan Time ကို ခန့်မှန်းရန်:

```bash
# Verbose mode shows scan progress and ETA
nmap -v -sS -p- 192.168.1.1

# Statistical progress (press SPACE during scan)
# Shows: completion %, time elapsed, ETA, rate

# Runtime interaction keys during scan:
# v/V - Increase/decrease verbosity
# d/D - Increase/decrease debug level
# p - Toggle packet tracing
```

---

### Performance Comparison Table

| Scenario | Recommended Settings | Expected Result |
|----------|---------------------|-----------------|
| Internal LAN, full scan | `-T4 -p- --min-rate 1000` | Minutes |
| Remote, stealth needed | `-T2 --max-retries 2 --scan-delay 1s` | Hours |
| Pentest (balanced) | `-T4 -A -sV -sC` | 10-30 min per host |
| Massive range, host discovery only | `-sn -T5 --min-hostgroup 256` | Minutes |
| UDP (optimized) | `-sU -p common --max-retries 1 --host-timeout 15m` | Depends heavily |

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 11.1: Timing Lab**

```bash
# Compare scan times at different timing levels
time nmap -T2 -p 1-1000 scanme.nmap.org
time nmap -T3 -p 1-1000 scanme.nmap.org
time nmap -T4 -p 1-1000 scanme.nmap.org

# Test with and without DNS
time nmap -T4 scanme.nmap.org
time nmap -n -T4 scanme.nmap.org

# Observe verbose output
nmap -v -T4 -p- scanme.nmap.org
```

---

### အကျဉ်းချုပ် (Summary)

- T4 သည် Real-World Engagement အတွက် အကောင်းဆုံး
- Multi-stage Approach သည် Large Network Scan အတွက် အထိရောက်ဆုံး
- UDP Scan နှင့် TCP Scan ကို သီးခြားစီလုပ်ပါ
- `-n` (no DNS) နှင့် `-Pn` (no ping) တို့ဖြင့် Scan Time လျှော့ချနိုင်

### Key Takeaways

| Goal | Technique |
|------|-----------|
| Maximum speed | `-T4` with `-n` |
| Maximum stealth | `-T0` or `-T1` |
| Rate limiting | `--max-rate` |
| Dead host timeout | `--host-timeout` |
| Defeat ICMP limit | `--defeat-icmp-ratelimit` |

---

## အခန်း ၁၂ — Firewall & IDS Evasion

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Firewall Detection Techniques များကို ကျွမ်းကျင်မည်
- Firewall Bypass နည်းလမ်းများကို သိရှိမည်
- IDS Evasion Techniques များကို လုပ်ဆောင်နိုင်မည်
- Packet Forgery Detection ကို နားလည်မည်

> **WARNING:** ဤအခန်းပါ Techniques များကို ခွင့်ပြုချက်ရှိသော Security Testing တွင်သာ အသုံးပြုရန်။ Unauthorized Firewall Evasion သည် ဥပဒေချိုးဖောက်မှု ဖြစ်နိုင်သည်။

---

### 12.1 Firewall Detection — Determining Firewall Rules

**Standard SYN Scan for Firewall Detection:**

Filtered Port များ၏ Pattern ကိုကြည့်၍ Firewall Rules ကို ခန့်မှန်းနိုင်သည်။

```bash
# Standard scan with reason output
nmap -sS --reason 192.168.1.1
# Shows WHY each port state was assigned
```

**ACK Scan for Firewall Mapping:**

```bash
nmap -sA 192.168.1.1
# Unfiltered = firewall allows traffic to port
# Filtered = firewall blocks traffic to port
```

ACK Scan သည် Firewall Stateful Inspection Rules ကို Map လုပ်ရန် အသုံးဝင်သည်။

---

### 12.2 Fragmentation (-f, --mtu)

**Command:**
```
nmap -f 192.168.1.1
nmap -ff 192.168.1.1    # Double fragmentation
nmap --mtu 8 192.168.1.1
```

**How it works internally:**
IP Packet ကို 8-byte အပိုင်းအစများအဖြစ် ခွဲ၍ပို့သည်။ Firewall/IDS အချို့သည် Fragmented Packets များကို Reassemble မလုပ်နိုင်သောကြောင့် Bypass ဖြစ်နိုင်သည်။

**Syntax:**
- `-f`: 8-byte fragments (after IP header)
- `-ff`: Double 8-byte fragments (16 bytes total)
- `--mtu <N>`: Custom fragment size (multiple of 8)

> **Note:** Modern IDS/IPS အများစုသည် Fragmentation ကို သိရှိပြီးဖြစ်သည်။ ထို့အပြင် အချို့ Firewall များသည် Fragmented Packets ကို Drop လုပ်တတ်သည်။

---

### 12.3 Decoys (-D)

**Command:**
```
nmap -D RND:10 192.168.1.1           # 10 random decoys
nmap -D 10.0.0.1,10.0.0.2,ME 192.168.1.1  # Specific decoys + real IP
nmap -D 10.0.0.1,10.0.0.2 192.168.1.1     # Decoys only (careful!)
```

**How it works internally:**
Target သို့ Spoofed Source IP များဖြင့် Probe များပို့သည်။ Target Log တွင် Decoy IP များနှင့်အတူ မိမိ၏ IP ကလည်း Scan လုပ်သူများထဲမှ တစ်ခုအဖြစ် ပေါ်မည်။

**Requirements:**
- Decoy IP များသည် Online ဖြစ်ရမည် (မဟုတ်ပါက SYN Flood ဖြစ်နိုင်)
- Ethically, decoy အဖြစ်သုံးသော IP ပိုင်ရှင်ထံမှ ခွင့်ပြုချက်ရယူသင့်

> **Warning:** Decoys သည် Bandwidth ပိုသုံးပြီး Scan Speed ကိုလည်း လျော့စေသည်။

---

### 12.4 Source Port Manipulation

**Command:**
```
nmap --source-port 53 192.168.1.1
nmap -g 80 192.168.1.1
```

**How it works internally:**
Source Port ကို Firewall က Allowed Port (e.g., DNS=53, HTTP=80) အဖြစ် Spoof လုပ်၍ Firewall Rule ကို ကျော်လွှားရန်ကြိုးပမ်းသည်။

**Purpose:** Misconfigured Firewalls များ၏ Rules များသည် Destination Port ကိုသာ ကြည့်ပြီး Source Port ကို မစစ်တတ်သောကြောင့် ဖြစ်နိုင်သည်။

---

### 12.5 MAC Address Spoofing

**Command:**
```
nmap --spoof-mac 00:11:22:33:44:55 192.168.1.1
nmap --spoof-mac Apple 192.168.1.1     # Random Apple MAC
nmap --spoof-mac 0 192.168.1.1         # Random MAC
```

**How it works internally:**
Local Network တွင် MAC Address ကို Spoof လုပ်၍ MAC-based Access Control ကို ကျော်လွှားရန် ကြိုးပမ်းသည်။

---

### 12.6 Proxies

**Command:**
```
nmap --proxies http://proxy:8080,http://proxy2:8080 192.168.1.1
```

**How it works internally:**
Scan ကို HTTP/SOCKS4 Proxy များမှတစ်ဆင့် လမ်းကြောင်းလွှဲ၍ ပြုလုပ်သည်။ Target က Proxy ၏ IP ကိုသာ မြင်ရမည်။

---

### 12.7 Source Routing

```bash
nmap --ip-options "L 10.0.0.1 192.168.1.1" target
nmap --ip-options "R" target   # Record route
```

Loose Source Routing (LSRR) သည် IP Packet ကို တိကျသော Path တစ်ခုအတိုင်း သွားစေရန် ကြိုးပမ်းသည်။ Modern Network Devices အများစုသည် Source Routing ကို Block လုပ်ထားသည်။

---

### 12.8 Multiple Ping Probes

```bash
nmap -PE -PS443 -PA80 -PP 10.0.0.0/24
```

ICMP ကို Block လုပ်ထားသော်လည်း TCP ကို ခွင့်ပြုသည့် Firewall ရှေ့တွင် ICMP, TCP SYN, TCP ACK, ICMP Timestamp များကို ပေါင်းစပ်၍ Host Discovery ပြုလုပ်ခြင်းသည် ထိရောက်မှုရှိသည်။

---

### 12.9 IDS Evasion — Timing-Based

```bash
# Slow down to evade IDS
nmap -T1 --scan-delay 5s 192.168.1.1

# Rate limiting
nmap --max-rate 10 192.168.1.1

# Scatter across network (not consecutive)
# Default: Nmap randomizes host order (already good for IDS evasion)
```

**Additional IDS Evasion Tips:**
- Probe များကို Host တစ်ခုပြီးတစ်ခု ဆက်တိုက် Scan မလုပ်ပဲ Network အနှံ့ Scatter လုပ်ပါ
- Fragmentation သုံးပါ (သို့သော် Modern IDS များက သိနိုင်)
- Nmap ၏ Default ဖြစ်သော Port Randomization နှင့် Host Randomization သည် IDS Evasion အတွက် အတော်အသင့် ထိရောက်ပြီးဖြစ်သည်

---

### 12.10 Detecting Packet Forgery

**Defenders ဘက်မှ Detection Methods:**

| Method | What It Detects |
|--------|-----------------|
| TTL Consistency | Spoofed packets often have different TTL |
| IP ID Consistency | Inconsistent IP ID values across probes |
| Bogus TCP Checksum | Certain IDS systems detect this |
| Round Trip Times | Decoys from distant IPs have different RTT |
| Packet Header Analysis | Anomalies in header fields |
| Network Uniformity | Unusual patterns across probes |

---

### Evasion Techniques Comparison Table

| Technique | Command | Effectiveness | Risk |
|-----------|---------|---------------|------|
| Fragmentation | `-f` | Low (modern) | Packets may be dropped |
| Decoys | `-D RND:10` | Medium | Bandwidth heavy, ethical concerns |
| Source Port | `--source-port 53` | Medium | Depends on firewall config |
| MAC Spoof | `--spoof-mac 0` | Low (LAN only) | Local network only |
| Idle Scan | `-sI zombie` | High | Requires idle zombie host |
| Timing | `-T0`, `-T1` | Medium | Very slow |
| Proxies | `--proxies` | High | Requires proxy |
| Multiple Pings | Combination | Medium-High | More traffic |

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

```bash
# Exercise 1: Check firewall rules with ACK scan
sudo nmap -sA 192.168.1.1

# Exercise 2: Fragmentation
sudo nmap -f -p 80 192.168.1.1

# Exercise 3: Decoy scan
sudo nmap -D RND:5 -p 80 scanme.nmap.org

# Exercise 4: Source port trick
sudo nmap --source-port 53 -p 22 192.168.1.1

# Exercise 5: Combined evasion
sudo nmap -f -D RND:3 --source-port 443 --data-length 50 -p 80 192.168.1.1
```

---

### အကျဉ်းချုပ် (Summary)

- Firewall Rules ကို ACK Scan, IP ID Tricks, UDP Version Scanning တို့ဖြင့် Map လုပ်နိုင်
- Fragmentation, Decoys, Source Port, Idle Scan, Proxies တို့သည် Firewall Bypass Techniques များဖြစ်သည်
- IDS Evasion အတွက် Slow Scan, Scattered Probing, Fragmentation တို့ကို အသုံးပြုနိုင်သည်
- Evasion Techniques အားလုံးတွင် Trade-offs (speed, accuracy, ethics) များရှိသည်

### Key Takeaways

| Goal | Best Technique |
|------|---------------|
| Firewall Mapping | `-sA` (ACK Scan) |
| IP Anonymity | `-sI` (Idle Scan) |
| Simple Evasion | `-f`, `--source-port`, `-D` |
| IDS Evasion | `-T1 --max-rate 10` |

---

## အခန်း ၁၃ — Output Formats

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Output Format အားလုံးကို ကျွမ်းကျင်မည်
- XML Output ကို Parse လုပ်နိုင်မည်
- Scan Results များကို မှန်ကန်စွာ သိမ်းဆည်းတတ်မည်
- Verbosity နှင့် Debugging Output ကို အသုံးပြုနိုင်မည်

---

### 13.1 Output Format Options

| Flag | Format | File Extension | Use Case |
|------|--------|---------------|----------|
| `-oN` | Normal | .nmap | Human-readable |
| `-oX` | XML | .xml | Programmatic parsing |
| `-oG` | Grepable | .gnmap | Command-line parsing (grep/awk) |
| `-oA` | All three | .nmap/.xml/.gnmap | Comprehensive |
| `-oS` | Script Kiddie | .nmap | Fun/"leet-speak" output |

---

### 13.2 Normal Output (-oN)

**Command:**
```
nmap -oN scan_results.txt 192.168.1.0/24
```

**Sample output:**
```
# Nmap 7.93 scan initiated Mon Jul 27 10:00:00 2026 as: nmap -oN scan.txt 192.168.1.0/24
Nmap scan report for 192.168.1.1
Host is up (0.0032s latency).
Not shown: 995 closed ports
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
443/tcp  open  https
MAC Address: XX:XX:XX:XX:XX:XX (Vendor)

# Nmap done at Mon Jul 27 10:05:00 2026 -- 256 IP addresses (4 hosts up) scanned in 300.50 seconds
```

**Characteristics:**
- Human-readable text format
- Includes scan metadata (version, timestamp, command)
- Each host has its own section
- Default format when using `>` redirection

---

### 13.3 XML Output (-oX)

**Command:**
```
nmap -oX scan_results.xml 192.168.1.1
```

**XML Structure:**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE nmaprun PUBLIC "-//IDN nmap.org//DTD Nmap XML 1.04//EN"
  "https://svn.nmap.org/nmap/docs/nmaprun.dtd">
<nmaprun scanner="nmap" ...>
  <scaninfo type="syn" protocol="tcp" .../>
  <host starttime="..." endtime="...">
    <status state="up" reason="arp-response"/>
    <address addr="192.168.1.1" addrtype="ipv4"/>
    <address addr="XX:XX:XX:XX:XX:XX" addrtype="mac" vendor="Vendor"/>
    <hostnames>
      <hostname name="router.local" type="PTR"/>
    </hostnames>
    <ports>
      <port protocol="tcp" portid="22">
        <state state="open" reason="syn-ack"/>
        <service name="ssh" product="OpenSSH" version="7.4" .../>
      </port>
    </ports>
    <os>
      <osmatch name="Linux 3.x" accuracy="95" line="1234">
        <osclass type="general purpose" vendor="Linux" osfamily="Linux"/>
      </osmatch>
    </os>
  </host>
  <runstats>
    <finished time="..." timestr="..." elapsed="14.40" .../>
  </runstats>
</nmaprun>
```

**Benefits of XML:**
- Machine-parseable (Python, Perl, Ruby scripts များဖြင့်)
- Complete metadata
- CPE (Common Platform Enumeration) support
- DTD validation
- HTML report generation support

---

### 13.4 Grepable Output (-oG)

**Command:**
```
nmap -oG hostdiscovery 192.168.1.0/24
```

**Grepable Format Fields:**

```
# Nmap 7.93 scan initiated ...
Host: 192.168.1.1 (router.local) Status: Up
Host: 192.168.1.1 (router.local) Ports: 22/open/tcp//ssh//OpenSSH 7.4/, 80/open/tcp//http//Apache httpd 2.4.7/
# Nmap done ...
```

**Command-line parsing:**

```bash
# Extract live hosts
awk '/Up$/{print $2}' scan.gnmap > live_hosts.txt

# Extract hosts with port 80 open
grep "80/open" scan.gnmap | awk '{print $2}'

# Extract all open ports for each host
grep "Ports:" scan.gnmap | awk -F'\t' '{print $2}'

# Count live hosts
grep -c "Status: Up" scan.gnmap
```

---

### 13.5 All Formats (-oA)

**Command:**
```
nmap -oA full_scan -p- -sS -sV -T4 -iL livehosts.txt
```

**Output files created:**
- `full_scan.nmap` — Normal text
- `full_scan.xml` — XML
- `full_scan.gnmap` — Grepable

---

### 13.6 Verbosity & Debugging Output

**Verbosity:**

```bash
nmap -v target    # Verbose — show open ports as discovered
nmap -vv target   # Very verbose — show timing details, warnings
```

**Debugging:**

```bash
nmap -d target    # Debug level 1
nmap -d2 target   # Debug level 2 (more detail)
nmap -d3 target   # Debug level 3 (extremely verbose)
```

**Packet Trace:**

```bash
nmap --packet-trace target   # Show ALL sent/received packets
```

---

### 13.7 Resuming Aborted Scans

```bash
# Save scan in all formats for resume capability
nmap -oA bigscan -p- 10.0.0.0/8

# If interrupted, resume:
nmap --resume bigscan.nmap
```

---

### 13.8 HTML Reports

Nmap XML Output ကို `xsltproc` သို့မဟုတ် Browser ဖြင့် HTML Report အဖြစ် ပြောင်းနိုင်သည်:

```bash
# Convert XML to HTML
xsltproc /usr/share/nmap/nmap.xsl scan.xml > scan.html

# Open in browser
firefox scan.html
```

---

### Output Format Comparison Table

| Feature | Normal (-oN) | XML (-oX) | Grepable (-oG) |
|---------|-------------|-----------|----------------|
| Human readable | Yes | Requires parser | Semi |
| Machine parseable | Difficult | Yes (XML) | Yes (awk/grep) |
| All metadata | Some | Complete | Limited |
| CPE support | No | Yes | No |
| Performance | Fast | Medium | Fast |
| Resume support | Yes | Yes | No |
| DTD validation | No | Yes | No |

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 13.1: Output Formats Lab**

```bash
# Exercise 1: Generate all output types
nmap -oA my_scan scanme.nmap.org

# Exercise 2: Compare formats
nmap -oN normal.txt scanme.nmap.org
nmap -oX xml.txt scanme.nmap.org
nmap -oG grep.txt scanme.nmap.org

# Exercise 3: Parse grepable output
awk '/open/{print $2}' grep.txt

# Exercise 4: Verbose with packet trace
nmap -vv --packet-trace -p 80 scanme.nmap.org

# Exercise 5: Generate HTML report
nmap -oX report.xml scanme.nmap.org
xsltproc /usr/share/nmap/nmap.xsl report.xml > report.html
```

---

### အကျဉ်းချုပ် (Summary)

| Format | Flag | Best For |
|--------|------|----------|
| Normal | `-oN` | Reading directly |
| XML | `-oX` | Parsing, HTML reports |
| Grepable | `-oG` | awk/grep filtering |
| All | `-oA` | Comprehensive |
| Script Kiddie | `-oS` | Fun only |

### Key Takeaways

- `-oA` is recommended for all important scans
- XML output enables HTML report generation
- Grepable output is best for quick CLI analysis
- Use `--resume` to continue interrupted scans
- Verbose (`-v`) mode is useful during scans, not for final output

---

## အခန်း ၁၄ — XML Processing

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Nmap XML Structure ကို နားလည်မည်
- XML Output ကို Script များဖြင့် Parse လုပ်နိုင်မည်
- Database Output ထုတ်လုပ်နိုင်မည်
- HTML Reports များ ဖန်တီးနိုင်မည်

---

### 14.1 Nmap XML DTD

Nmap XML Output တွင် Document Type Definition (DTD) ပါဝင်ပြီး XML Structure ကို အတည်ပြုနိုင်သည်။

**Key XML Elements:**

| Element | Contains |
|---------|----------|
| `<nmaprun>` | Root element — scan metadata |
| `<scaninfo>` | Scan type, protocol, ports scanned |
| `<host>` | Per-host results |
| `<status>` | Host state (up/down), reason |
| `<address>` | IP, MAC addresses |
| `<hostnames>` | DNS hostnames |
| `<ports>` | Port scan results |
| `<os>` | OS detection results |
| `<runstats>` | Scan statistics |

---

### 14.2 Parsing XML with Python

```python
#!/usr/bin/env python3
"""Parse Nmap XML output and extract key information."""

import xml.etree.ElementTree as ET

def parse_nmap_xml(xml_file):
    tree = ET.parse(xml_file)
    root = tree.getroot()

    for host in root.findall('host'):
        # Get IP address
        addr = host.find("address[@addrtype='ipv4']")
        if addr is None:
            continue

        ip = addr.get('addr')
        print(f"\nHost: {ip}")

        # Check status
        status = host.find('status')
        if status is not None:
            print(f"  Status: {status.get('state')}")

        # Get open ports
        ports = host.find('ports')
        if ports is not None:
            for port in ports.findall('port'):
                port_id = port.get('portid')
                state = port.find('state')
                service = port.find('service')

                if state is not None and state.get('state') == 'open':
                    svc_name = service.get('name', 'unknown') if service is not None else 'unknown'
                    svc_product = service.get('product', '') if service is not None else ''
                    print(f"  Port {port_id}: {svc_name} {svc_product}")

if __name__ == '__main__':
    import sys
    if len(sys.argv) > 1:
        parse_nmap_xml(sys.argv[1])
    else:
        print("Usage: python3 parse_nmap.py scan.xml")
```

**Run:**

```bash
nmap -oX scan.xml 192.168.1.1
python3 parse_nmap.py scan.xml
```

---

### 14.3 HTML Report Generation

```bash
# Method 1: XSLT Processor
nmap -oX scan.xml 192.168.1.0/24
xsltproc -o scan.html /usr/share/nmap/nmap.xsl scan.xml

# Method 2: Python
# Use libraries like jinja2 to create custom HTML templates
```

---

### 14.4 Database Storage

Nmap XML can be imported into databases for long-term storage and analysis.

**SQL Database Import (Conceptual):**

```python
# Insert into SQLite database
import sqlite3
conn = sqlite3.connect('scans.db')
c = conn.cursor()
c.execute('''CREATE TABLE IF NOT EXISTS hosts
             (ip TEXT, hostname TEXT, scan_date TEXT)''')
c.execute('''CREATE TABLE IF NOT EXISTS ports
             (ip TEXT, port INTEGER, protocol TEXT, state TEXT, service TEXT)''')

# Parse XML and insert records...
```

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

```bash
# Exercise 1: Generate XML and view structure
nmap -oX example.xml -sV scanme.nmap.org
python3 -c "import xml.dom.minidom; print(xml.dom.minidom.parse('example.xml').toprettyxml())" | head -50

# Exercise 2: Generate HTML report
xsltproc /usr/share/nmap/nmap.xsl example.xml > report.html

# Exercise 3: Write a simple parser
# Use the Python script above to extract open ports
```

---

### အကျဉ်းချုပ် (Summary)

- Nmap XML follows a well-defined DTD with elements for hosts, ports, services, and OS
- Python's `xml.etree.ElementTree` can parse Nmap XML output
- `xsltproc` converts XML to HTML reports using `nmap.xsl`
- XML output enables database storage and historical analysis

---

## အပိုင်း ၄ — Practical Applications

---

## အခန်း ၁၅ — Practical Network Enumeration

### သင်ယူမှုရည်ရွယ်ချက်များ (Learning Objectives)

ဤအခန်းပြီးဆုံးပါက သင်သည်:
- Internal/External Network Scanning Workflow ကို ကျွမ်းကျင်မည်
- Service Inventory ပြုလုပ်နိုင်မည်
- Network Mapping Techniques ကို လုပ်ဆောင်နိုင်မည်
- Real-World Penetration Testing အတွက် Practical Scenarios များကို ကိုင်တွယ်နိုင်မည်

---

### 15.1 Complete Penetration Testing Workflow

Penetration Test တစ်ခုအတွက် Standard Nmap Workflow:

```
Step 1: Host Discovery
   ↓
Step 2: Live Host List Creation
   ↓
Step 3: Top Port Scan on Live Hosts
   ↓
Step 4: Full Port Scan on Critical Hosts
   ↓
Step 5: Service/Version Detection
   ↓
Step 6: NSE Script Scanning
   ↓
Step 7: Output & Reporting
```

---

### 15.2 Internal Network Scanning

**Scenario:** Internal LAN 192.168.1.0/24 ကို Full Assessment ပြုလုပ်ခြင်း

```bash
# Step 1: Quick host discovery (ARP + ICMP)
nmap -sn -T4 192.168.1.0/24 -oA step1_hosts

# Step 2: Extract live hosts
awk '/Up$/{print $2}' step1_hosts.gnmap > live_hosts.txt

# Step 3: Top 1000 TCP ports on all live hosts
nmap -sS -sV --top-ports 1000 -T4 -iL live_hosts.txt -oA step2_tcp

# Step 4: Common UDP ports
nmap -sU -sV -p 53,67,68,69,123,161,500,1900 -T4 -iL live_hosts.txt -oA step3_udp

# Step 5: Full scan on critical hosts
nmap -sS -sV -sC -p- -T4 -iL critical_hosts.txt -oA step4_full

# Step 6: Vulnerability scanning
nmap -sV --script vuln -iL live_hosts.txt -oA step5_vuln
```

---

### 15.3 Service Inventory

Network တစ်ခုလုံးရှိ Service များကို Inventory ပြုလုပ်ရန်:

```bash
# Scan all common services across subnet
nmap -sV -p 21,22,23,25,53,80,111,135,139,443,445,902,1433,3306,3389,5432,5900,8080 -T4 192.168.1.0/24 -oA service_inventory

# Extract summary of services found
grep -h "open" service_inventory.gnmap | awk -F'/' '{print $5}' | sort | uniq -c | sort -rn
```

---

### 15.4 Network Mapping

```bash
# Traceroute + OS Detection for network topology
nmap -A --traceroute 192.168.1.0/24 -oA network_map

# Find routers/gateways
nmap -p 22,23,80,443 --open 192.168.1.1-10 -oG routers.txt
```

---

### Real-World Example: EternalBlue Scan

```bash
# Scan entire network for MS17-010 vulnerability
nmap -Pn -p 445 --script smb-vuln-ms17-010 192.168.1.0/24 -oN eternalblue.txt

# Check results
grep "VULNERABLE" eternalblue.txt
```

---

### Real-World Example: HTTP Servers + Nikto

```bash
# Find HTTP servers and pipe to Nikto
nmap -p 80,443 192.168.1.0/24 -oG - | awk '/open/{print $2}' > http_hosts.txt

# Run Nikto on each HTTP host
while read host; do
    nikto -h $host -o nikto_$host.txt
done < http_hosts.txt
```

---

### Real-World Example: Geo Location Check

```bash
nmap --script=ip-geolocation-ipinfodb \
  --script-args=ip-geolocation-ipinfodb.apikey=YOUR_API_KEY \
  8.8.8.8
# Shows: city, country, coordinates
```

---

### Real-World Example: WAF Detection

```bash
nmap -p 80,443 --script http-waf-detect \
  --script-args="http-waf-detect.aggro,http-waf-detect.detectBodyChanges" \
  www.example.com
```

---

### လက်တွေ့လေ့ကျင့်ခန်း (Hands-on Lab)

**Lab 15.1: Full Network Assessment**

```bash
# Setup: Lab environment with virtual machines

# Exercise 1: Complete host discovery
nmap -sn 192.168.1.0/24 -oA lab_hosts

# Exercise 2: Service inventory
nmap -sV -F -iL lab_hosts.txt -oA lab_services

# Exercise 3: Vulnerability check
nmap -sV --script vuln -iL lab_hosts.txt -oA lab_vuln

# Exercise 4: Generate report
nmap -oX lab_final.xml -A -iL lab_hosts.txt
```

---

### အကျဉ်းချုပ် (Summary)

- Multi-stage scanning (host discovery → port scan → service detection → vuln check) သည် အထိရောက်ဆုံး
- Internal scans are faster and more thorough than external scans
- `awk` and `grep` with Grepable output is powerful for automation
- Always save intermediate results for each stage

### Key Takeaways

| Stage | Command Pattern |
|-------|----------------|
| Host Discovery | `nmap -sn -T4` |
| Service Inventory | `nmap -sV -F` |
| Full Port Scan | `nmap -sS -sV -p-` |
| Vulnerability | `nmap -sV --script vuln` |
| Output | `-oA` for all stages |

---


## အခန်း ၁၆ — Service-Specific Enumeration

### သင်ယူမှုရည်ရွယ်ချက်များ

ဤအခန်းပြီးဆုံးပါက သင်သည် Service အလိုက် Enumeration Techniques များကို ကျွမ်းကျင်မည်။

---

### 16.1 Web Server Enumeration

**Target Ports:** 80, 443, 8080, 8443

```bash
nmap -p 80,443 --script http-title,http-headers,http-server-header 192.168.1.1
nmap -p 80,443 --script http-methods 192.168.1.1
nmap -p 80,443 --script http-enum 192.168.1.1
nmap -p 80,443 --script http-waf-detect,http-waf-fingerprint www.example.com
nmap -p 80,443 --script http-shellshock --script-args http-shellshock.uri=/cgi-bin/test.cgi 192.168.1.1
nmap -p 80,443 --script "http-* and safe" 192.168.1.1
```

---

### 16.2 SMB Enumeration

**Target Ports:** 139 (NetBIOS), 445 (SMB)

```bash
nmap -p 139,445 --script smb-os-discovery 192.168.1.0/24
nmap -p 445 --script smb-enum-shares,smb-enum-users 192.168.1.1
nmap -p 445 --script smb-vuln-ms17-010 192.168.1.0/24
nmap -p 139,445 --script "smb-* and safe" -sV 192.168.1.1
```

---

### 16.3 DNS Enumeration

**Target Port:** 53

```bash
nmap -p 53 --script dns-recursion 192.168.1.1
nmap -p 53 --script dns-zone-transfer --script-args dns-zone-transfer.server=ns1.domain.com domain.com
nmap -p 53 --script dns-brute --script-args dns-brute.domain=domain.com domain.com
```

---

### 16.4 Email (SMTP) Enumeration

**Target Ports:** 25, 465, 587

```bash
nmap -p 25 --script smtp-commands,smtp-enum-users,smtp-open-relay 192.168.1.1
```

---

### 16.5 FTP Enumeration

**Target Port:** 21

```bash
nmap -p 21 --script ftp-anon 192.168.1.1
nmap -p 21 --script ftp-proftpd-backdoor,ftp-vsftpd-backdoor 192.168.1.1
```

---

### 16.6 SSH Enumeration

**Target Port:** 22

```bash
nmap -p 22 --script ssh-hostkey --script-args ssh_hostkey=full 192.168.1.1
nmap -p 22 --script ssh2-enum-algos,ssh-auth-methods 192.168.1.1
```

---

### 16.7 Database Enumeration

```bash
# MySQL (3306)
nmap -p 3306 --script mysql-empty-password,mysql-info,mysql-enum 192.168.1.1
# PostgreSQL (5432)
nmap -p 5432 --script pgsql-brute 192.168.1.1
# MSSQL (1433)
nmap -p 1433 --script ms-sql-info,ms-sql-config 192.168.1.1
```

---

### 16.8 SSL/TLS Analysis

```bash
nmap -p 443 --script ssl-enum-ciphers,ssl-cert 192.168.1.1
nmap -p 443 --script ssl-heartbleed,ssl-poodle,ssl-ccs-injection 192.168.1.1
```

### Service Cheat Sheet

| Service | Port | Key Scripts |
|---------|------|-------------|
| HTTP/S | 80,443 | http-title, http-enum, http-waf-detect |
| SMB | 139,445 | smb-os-discovery, smb-enum-shares, smb-vuln-ms17-010 |
| DNS | 53 | dns-brute, dns-zone-transfer, dns-recursion |
| SMTP | 25,465,587 | smtp-commands, smtp-enum-users, smtp-open-relay |
| FTP | 21 | ftp-anon |
| SSH | 22 | ssh-hostkey, ssh2-enum-algos |
| MySQL | 3306 | mysql-empty-password, mysql-enum |
| SSL/TLS | 443 | ssl-enum-ciphers, ssl-cert, ssl-heartbleed |

### အကျဉ်းချုပ်

- Service တစ်ခုစီတွင် Dedicated NSE Scripts အများအပြားရှိသည်
- `--script "xxx-* and safe"` ဖြင့် Safe Scripts ကိုသာ သုံးပါ
- Version Detection (-sV) ကို အမြဲပူးတွဲသုံးပါ

---

## အခန်း ၁၇ — Active Directory Enumeration

### သင်ယူမှုရည်ရွယ်ချက်များ

ဤအခန်းပြီးဆုံးပါက သင်သည် Active Directory Environment ကို Nmap ဖြင့် Enumerate လုပ်နိုင်မည်။

---

### 17.1 Domain Controller Discovery

**Key Ports:**

| Port | Service | Purpose |
|------|---------|---------|
| 88 | Kerberos | Authentication |
| 389 | LDAP | Directory queries |
| 636 | LDAPS | Secure LDAP |
| 3268 | Global Catalog | Forest-wide search |
| 3269 | GC over SSL | Secure GC |

```bash
nmap -p 88,389,636,3268,3269 --open 192.168.1.0/24
nmap -O -p 88,389 --open 192.168.1.0/24
nmap -sV -p 88,389,636,3268,3269 192.168.1.0/24
```

### 17.2 LDAP & SMB Enumeration

```bash
nmap -p 389 --script ldap-rootdse 192.168.1.1
nmap -p 445 --script smb-os-discovery,smb-enum-shares,smb-enum-users,smb-enum-groups 192.168.1.1
nmap -p 88 --script krb5-enum-users --script-args krb5-enum-users.realm=DOMAIN.LOCAL 192.168.1.1
```

### AD Enumeration Workflow

```bash
# Step 1: Find domain controllers
nmap -sn 192.168.1.0/24 -oA discovery
nmap -p 88,389 --open -iL <(awk '/Up/{print $2}' discovery.gnmap) -oA dc_candidates

# Step 2: Enumerate DC services
nmap -sV -sC -p 88,389,445 -iL dc_ips.txt -oA dc_enum

# Step 3: Full AD enumeration
nmap -p 88,389,445 --script "ldap-*,smb-enum-*,krb5-*" -iL dc_ips.txt -oA ad_full
```

### အကျဉ်းချုပ်

- DC found via Kerberos (88), LDAP (389), Global Catalog (3268)
- SMB enumeration (445) provides rich AD information
- LDAP NSE scripts may require valid credentials

---

## အခန်း ၁၈ — Vulnerability Detection

### သင်ယူမှုရည်ရွယ်ချက်များ

ဤအခန်းပြီးဆုံးပါက သင်သည် NSE Scripts များဖြင့် Vulnerability Detection ပြုလုပ်နိုင်မည်။

---

```bash
# Run all vuln scripts
nmap -sV --script vuln 192.168.1.1

# EternalBlue (MS17-010)
nmap -Pn -p 445 --script smb-vuln-ms17-010 192.168.1.0/24 -oN eternalblue.txt

# Heartbleed
nmap -p 443 --script ssl-heartbleed 192.168.1.0/24

# Shellshock
nmap -p 80,443 --script http-shellshock --script-args uri=/cgi-bin/test.cgi 192.168.1.1

# POODLE, CCS Injection
nmap -p 443 --script ssl-poodle,ssl-ccs-injection 192.168.1.1

# CVE Lookup (Vulners)
cd /usr/share/nmap/scripts/ && git clone https://github.com/vulnersCom/nmap-vulners.git
nmap --script-updatedb
nmap -sV --script vulners -p 22,80,443,3306 192.168.1.1
```

### အကျဉ်းချုပ်

- NSE `vuln` category သည် Vulnerability Detection Scripts များဖြစ်သည်
- `-sV` သည် Vulnerability Scanning မပြုမီ မဖြစ်မနေလိုအပ်
- EternalBlue, Heartbleed, Shellshock အတွက် Dedicated Scripts ရှိ
- Vulners script သည် CVE Database Cross-reference လုပ်ပေးသည်

---

## အခန်း ၁၉ — Bash Automation

### သင်ယူမှုရည်ရွယ်ချက်များ

ဤအခန်းပြီးဆုံးပါက သင်သည် Bash Scripts များဖြင့် Nmap ကို Automate လုပ်နိုင်မည်।

---

### Basic Automation Script

```bash
#!/bin/bash
TARGET=$1
TIMESTAMP=$(date +%Y%m%d_%H%M%S)
OUTDIR="scans/$TIMESTAMP"
mkdir -p $OUTDIR
echo "[+] Scanning $TARGET"
nmap -sS -sV -T4 $TARGET -oA "$OUTDIR/tcp_scan"
nmap -sU -sV -p 53,123,161 $TARGET -oA "$OUTDIR/udp_scan"
echo "[+] Done. Results in $OUTDIR"
```

### Bulk Subnet Scanning

```bash
#!/bin/bash
SUBNETS=("192.168.1.0/24" "192.168.2.0/24" "10.0.0.0/24")
DATE=$(date +%Y%m%d)
for subnet in "${SUBNETS[@]}"; do
    nmap -sn -T4 $subnet -oA "scans/$DATE/${subnet//\//_}_hosts"
    awk '/Up$/{print $2}' "scans/$DATE/${subnet//\//_}_hosts.gnmap" > "scans/$DATE/${subnet//\//_}_live.txt"
    nmap -sS -sV -T4 -iL "scans/$DATE/${subnet//\//_}_live.txt" -oA "scans/$DATE/${subnet//\//_}_services"
done
```

### Output Parsing

```bash
grep "22/open" scan.gnmap | awk '{print $2}'     # IPs with SSH
grep -h "open" *.gnmap | awk -F'/' '{print $5}' | sort -u  # Unique services
awk '/Up$/{print $2}' scan.gnmap > live_hosts.txt            # Live hosts
```

### Cron Scheduling & Ndiff

```bash
# Weekly scan with change detection
WEEK=$(date +%Y-W%U)
nmap -oA "/var/log/nmap/weekly_$WEEK" -sV 192.168.1.0/24
ndiff "/var/log/nmap/weekly_$(date -d 'last week' +%Y-W%U).xml" \
      "/var/log/nmap/weekly_$WEEK.xml" > "/var/log/nmap/diff_$WEEK.txt"
```

### အကျဉ်းချုပ်

- Bash + awk + grep = Powerful CLI automation
- Grepable output is ideal for parsing
- Ndiff for change detection
- Cron for scheduled regular scanning

---

## အခန်း ၂၀ — Python Automation

### သင်ယူမှုရည်ရွယ်ချက်များ

ဤအခန်းပြီးဆုံးပါက သင်သည် Python scripts များဖြင့် Nmap ကို Automate လုပ်နိုင်မည်။

---

### Using python-nmap

```bash
pip install python-nmap
```

```python
import nmap
nm = nmap.PortScanner()
nm.scan('scanme.nmap.org', '22,80,443', '-sV')
for host in nm.all_hosts():
    print(f"{host}: {nm[host].state()}")
    for proto in nm[host].all_protocols():
        for port in nm[host][proto]:
            print(f"  {port}/{proto}: {nm[host][proto][port]['state']}")
```

### Parsing XML Output

```python
import xml.etree.ElementTree as ET
tree = ET.parse('scan.xml')
for host in tree.findall('host'):
    addr = host.find("address[@addrtype='ipv4']")
    ports = host.find('ports')
    if addr is not None and ports is not None:
        ip = addr.get('addr')
        print(f"Host: {ip}")
        for port in ports.findall('port'):
            state = port.find('state')
            if state.get('state') == 'open':
                svc = port.find('service')
                name = svc.get('name') if svc is not None else '?'
                print(f"  {port.get('portid')}/tcp - {name}")
```

### Key Libraries

| Task | Library |
|------|---------|
| Scan from Python | `python-nmap` |
| XML parsing | `xml.etree.ElementTree` |
| Web dashboard | Flask + Nmap XML |
| Change detection | `ndiff` (CLI) |

### အကျဉ်းချုပ်

- `python-nmap` provides a clean programmatic Nmap API
- XML + ElementTree = robust parsing
- Python enables web dashboards, databases, full custom scanner apps

---


## အပိုင်း ၅ — Professional Practice

---

## အခန်း ၂၁ — Safe Security Assessment

### Rules of Engagement

1. **Scope:** မည်သည့် IP Range, Subnets, Hosts များကို Scan လုပ်မည်ကို အတိအကျသတ်မှတ်ပါ
2. **Timing:** Business hours ပြင်ပတွင် Scan ပြုလုပ်ပါ
3. **Techniques:** ခွင့်ပြုထားသော Scan Type များကို အတည်ပြုပါ
4. **Exclusions:** Critical Systems နှင့် Sensitive Host များကို `--exclude` လုပ်ပါ
5. **Contact:** ပြဿနာတက်ပါက ချက်ချင်းဆက်သွယ်ရမည့်သူ

### Safe Scanning Parameters

```bash
nmap -T3 \
     --max-rate 100 \
     --max-retries 2 \
     --host-timeout 10m \
     --scan-delay 500ms \
     -p common \
     --exclude sensitive_host1,sensitive_host2 \
     192.168.1.0/24
```

### Scan Speed vs Safety

| Speed | Risk | When to Use |
|-------|------|-------------|
| T0-T1 | Very Low | Critical production systems |
| T2 | Low | Cautious production scan |
| T3 | Medium | Standard assessment |
| T4 | Medium-High | Internal lab, CTF |
| T5 | High | Lab only |

> **Best Practice:** Production systems တွင် T2 သို့မဟုတ် T3 ဖြင့် စတင်ပါ။ Off-peak hours တွင် Scan လုပ်ပါ။ First scan တွင် `-F` (fast) သို့မဟုတ် `--top-ports 100` ဖြင့်စ၍ တဖြည်းဖြည်းချဲ့ပါ။

---

## အခန်း ၂၂ — Reporting

### Report Generation Steps

1. Raw scan data ကို `-oA` ဖြင့် စုဆောင်းပါ
2. XML ကို Parse လုပ်၍ Structured Data ထုတ်ယူပါ
3. Key Findings များကို Extract လုပ်ပါ
4. HTML Report Generate လုပ်ပါ (`xsltproc`)
5. Executive Summary ရေးသားပါ
6. Remediation Recommendations ထည့်သွင်းပါ

### Using Ndiff

```bash
# Baseline
nmap -oA baseline -sV 192.168.1.0/24
# Later
nmap -oA followup -sV 192.168.1.0/24
# Compare
ndiff baseline.xml followup.xml > changes.txt
```

Ndiff shows: New ports, closed ports, version changes, OS changes, host up/down status.

### HTML Report

```bash
nmap -oX scan.xml 192.168.1.0/24
xsltproc /usr/share/nmap/nmap.xsl scan.xml > report.html
```

---

## အခန်း ၂၃ — Troubleshooting & Common Errors

### Permission Errors

| Error | Solution |
|-------|----------|
| `root privileges required` | Use `sudo` or Administrator |
| `dnet: Failed to open device` | Install Npcap (Windows) or libpcap (Linux) |
| `operation not permitted` | Run with elevated privileges |

### Network Issues

| Error | Solution |
|-------|----------|
| `Host seems down` | Use `-Pn` to skip host discovery |
| `All 1000 ports filtered` | Firewall blocking; try `-sA` or `-Pn` |
| Scan too slow | Use `-T4`, `-n`, `--max-retries 1` |
| UDP scan hangs | `--host-timeout 15m`, `--max-retries 1` |

### False Positives vs False Negatives

| Issue | Cause | Mitigation |
|-------|-------|------------|
| Ports show filtered | Firewall/IDS | `-Pn`, `-sA`, `--reason` |
| All UDP ports open|filtered | ICMP blocked | `-sV` to verify, check with `--packet-trace` |
| Service version wrong | Probe mismatch | `--version-all` for thorough check |
| OS detection wrong | Insufficient ports | Ensure one open + one closed port |

### Common Mistakes

1. Default scan ကို Port 1000 သာစစ်သည်ဟု မေ့ခြင်း → `-p-`
2. T5 ကို Remote Network တွင် အသုံးပြုခြင်း → T4 recommended
3. `-Pn` ကို Subnet တစ်ခုလုံးတွင် သုံး၍ Dead Hosts များအား Scan လုပ်မိခြင်း
4. DNS Resolution (`-n` မသုံးဘဲ) ကြောင့် Slow Scan

---

## အခန်း ၂၄ — Best Practices

### Scanning Methodology

1. **Start with discovery:** `-sn` to identify live hosts
2. **Top ports first:** `--top-ports 100` then expand
3. **Service detection:** `-sV` on confirmed open ports
4. **Vulnerability scan:** `--script vuln` last
5. **Document everything:** `-oA` for every scan

### Documentation

- Every scan saves: timestamp, command, output
- Baseline scans for comparison
- Log all changes with Ndiff

### Reducing False Positives

- Verify with multiple scan types (SYN + Connect)
- Use `--reason` to understand state assignments
- Check with `--packet-trace` for packet-level analysis
- Wireshark for independent verification

### Legal Compliance

- Written authorization before any scan
- Respect scope boundaries
- Report findings responsibly
- Comply with data protection regulations

---

## အခန်း ၂၅ — Lab Exercises

### Setting Up a Lab Environment

- VirtualBox/VMware with Kali Linux + target VMs (Metasploitable, Ubuntu, Windows)
- Isolated network (Host-Only or NAT Network)
- Docker containers for quick service deployment

### Beginner Exercises

1. Install Nmap and verify with `nmap -V`
2. Run default scan on scanme.nmap.org: `nmap scanme.nmap.org`
3. Scan specific ports: `nmap -p 22,80,443 scanme.nmap.org`
4. Ping sweep your local network: `nmap -sn 192.168.1.0/24`
5. Save output to file: `nmap -oN scan.txt scanme.nmap.org`

### Intermediate Exercises

1. TCP SYN vs Connect scan comparison: Compare `-sS` and `-sT` results
2. UDP scan on DNS and SNMP: `nmap -sU -p 53,161 target`
3. Service version detection: `nmap -sV -p 1-1000 target`
4. Full port scan: `nmap -p- -T4 target`
5. OS detection with guess: `sudo nmap -O --osscan-guess target`

### Advanced Exercises

1. Write NSE scan script: `nmap --script "http-*" -p 80 target`
2. Firewall detection: `nmap -sA target` and interpret filtered/unfiltered
3. Fragment scan: `sudo nmap -f -p 80 target`
4. Idle scan (find zombie first): `sudo nmap -sI zombie_ip target`
5. Custom scanflags: `nmap --scanflags SYNFIN target`

### Expert Challenges

1. Design a complete PT workflow script (Bash) with all phases
2. Automate vulnerability assessment with Python + python-nmap
3. Bypass firewall using decoys + fragmentation + source port
4. Full AD enumeration workflow
5. Create an HTML dashboard from multiple Nmap XML outputs

---

## အခန်း ၂၆ — Review Questions

### Beginner Level (20 Questions)

1. Nmap ၏ အဓိကလုပ်ဆောင်ချက် (၄) ခုကား အဘယ်နည်း။
2. Default Nmap scan သည် Port မည်မျှကို Scan ပြုလုပ်သနည်း။
3. `-sn` Option ၏ အဓိပ္ပာယ်ကား အဘယ်နည်း။
4. TCP Three-Way Handshake ကို ရှင်းပြပါ။
5. Port States (open, closed, filtered) တစ်ခုစီကို ရှင်းပြပါ။
6. `-sV` နှင့် `-O` ၏ ကွာခြားချက်ကား အဘယ်နည်း။
7. Specified port ဖြင့် scan လုပ်ရန် command ကိုရေးပါ။
8. `-A` Option တွင် အဘယ်သည်တို့ ပါဝင်သနည်း။
9. UDP နှင့် TCP ၏ အဓိက ကွာခြားချက်ကား အဘယ်နည်း။
10. Nmap output format (၃) မျိုးကား အဘယ်နည်း။
11. `-Pn` ကို မည်သည့်အခါတွင် အသုံးပြုသင့်သနည်း။
12. Timing Templates တွင် T0 မှ T5 အထိ T3 သည် မည်သည့်အမျိုးအစားနည်း။
13. Subnet တစ်ခုလုံးကို Scan ရန် CIDR Notation ဖြင့် command ရေးပါ။
14. `--script` Option ကို အသုံးပြု၍ HTTP title ရယူရန် command ရေးပါ။
15. Port 22, 80, 443 ကိုသာ scan လုပ်ရန် command ရေးပါ။
16. `-v` နှင့် `-vv` ၏ ကွာခြားချက်ကား အဘယ်နည်း။
17. Grepable output မှ live hosts များကို မည်သို့ extract လုပ်မည်နည်း။
18. Windows target တွင် FIN Scan အလုပ်မလုပ်ရသည့် အကြောင်းရင်းကို ရှင်းပြပါ။
19. NSE ၏ အားသာချက်ကား အဘယ်နည်း။
20. Scan result ကို File တွင် သိမ်းဆည်းရန် command ရေးပါ။

### Intermediate Level (20 Questions)

1. SYN Scan နှင့် TCP Connect Scan ၏ Internal Mechanism ကွာခြားချက်ကို ရှင်းပြပါ။
2. UDP Scan တွင် Port Open နှင့် Closed ကို Nmap မည်သို့ခွဲခြားသနည်း။
3. Nmap ၏ Scan Phases (၉) ဆင့်ကို စာရင်းပြုစုပါ။
4. `--reason` Option ၏ အသုံးဝင်ပုံကား အဘယ်နည်း။
5. Idle Scan (-sI) ၏ Working Principle ကို ရှင်းပြပါ။
6. Timing Template T4 တွင် မည်သည့် Parameters များ သတ်မှတ်ထားသနည်း။ (၃ ခု)
7. IP Protocol Scan (-sO) ကို မည်သည့်အတွက် အသုံးပြုသနည်း။
8. `--defeat-rst-ratelimit` ၏ အသုံးပြုပုံကား အဘယ်နည်း။
9. Nmap XML Output ၏ Key Elements (၅) ခုကို စာရင်းပြုစုပါ။
10. Fragmentation (-f) သည် Firewall ကို မည်သို့ကျော်လွှားရန် ကြိုးပမ်းသနည်း။
11. NSE Script Categories (၈) ခုကို စာရင်းပြုစုပါ။
12. Version Detection Intensity Level များ၏ ကွာခြားချက်ကို ရှင်းပြပါ။
13. Multi-stage Scanning Strategy ကို ရှင်းပြပါ။
14. `ndiff` ၏ အသုံးပြုပုံကို ဥပမာဖြင့် ရှင်းပြပါ।
15. FIN, NULL, XMAS Scan တို့၏ ကွာခြားချက်များကား အဘယ်နည်း။
16. `nmap-service-probes` File ၏ အခန်းကဏ္ဍကား အဘယ်နည်း။
17. `--max-rate` နှင့် `--min-rate` ၏ ကွာခြားချက်ကား အဘယ်နည်း။
18. NSE Script တစ်ခု၏ Structure (Head, Rule, Action) ကို ရှင်းပြပါ။
19. Decoys (-D) ၏ အားသာချက်နှင့် အားနည်းချက်များကား အဘယ်နည်း။
20. `--exclude` ကို မည်သည့်အခြေအနေတွင် အသုံးပြုသင့်သနည်း။ (၂ ချက်)

### Advanced Level (20 Questions)

1. Nmap ၏ Congestion Control Algorithm အလုပ်လုပ်ပုံကို ရှင်းပြပါ။
2. OS Detection တွင် Sequence Generation Probes (SEQ, OPS, WIN, T1) ၏ အခန်းကဏ္ဍကား အဘယ်နည်း။
3. Idle Scan အတွက် Zombie Host တစ်ခု၏ လိုအပ်သော အရည်အသွေး (၃) ချက်ကား အဘယ်နည်း။
4. NSE Parallelism (Worker Threads, Mutexes, Condition Variables) ကို ရှင်းပြပါ။
5. Custom `nmap-service-probes` Entry တစ်ခုတွင် `Probe`, `match`, `softmatch` Directives များကို ရှင်းပြပါ။
6. `--scanflags` ဖြင့် Custom Scan Type ပြုလုပ်နည်းကို ဥပမာဖြင့် ရှင်းပြပါ။
7. Python `xml.etree.ElementTree` ဖြင့် Nmap XML မှ OS Detection Results ထုတ်ယူနည်းကို ရေးပါ။
8. Firewall Detection တွင် ACK Scan နှင့် IP ID Tricks တို့၏ ကွာခြားချက်ကား အဘယ်နည်း။
9. Nmap သည် Scan Delay ကို Adaptive အနေဖြင့် မည်သို့ထိန်းညှိသနည်း။
10. OS Detection ၏ Response Tests (GCD, ISR, SP, TI, CI, II) တို့ကို ရှင်းပြပါ။
11. NSE Scripting တွင် `prerule`, `hostrule`, `portrule`, `postrule` တို့၏ Run Order ကား အဘယ်နည်း။
12. `--defeat-icmp-ratelimit` ၏ အလုပ်လုပ်ပုံနှင့် မည်သည့် OS အတွက် အသုံးဝင်သနည်း။
13. Nmap Data Files (၇) ခု၏ တည်နေရာနှင့် အသုံးပြုပုံကို စာရင်းပြုစုပါ။
14. `--resume` Option ဖြင့် Aborted Scan ကို မည်သို့ပြန်စနိုင်သနည်း။
15. Source Port Manipulation နှင့် Idle Scan တို့၏ Firewall Evasion Mechanism ကွာခြားချက်ကား အဘယ်နည်း။
16. Nmap ၏ `nmap-os-db` File Format (Subject Fingerprint vs Reference Fingerprint) ကို ရှင်းပြပါ။
17. XML DTD Validation ၏ အရေးပါမှုနှင့် Nmaprun DTD Structure ကား အဘယ်နည်း။
18. NSE Library (`stdnse`, `shortport`, `http`, `smb`) တစ်ခုစီ၏ အသုံးပြုပုံကို ရှင်းပြပါ။
19. `--host-timeout`, `--max-retries`, `--scan-delay` တို့၏ Interaction ကို ရှင်းပြပါ။
20. Production Environment တွင် Safe Scanning အတွက် Comprehensive Strategy တစ်ခုကို Design လုပ်ပါ။

---

## အခန်း ၂၇ — Cheat Sheets

### 27.1 Command Quick Reference

**Target Specification:**

| Command | Description |
|---------|-------------|
| `nmap 10.0.0.1` | Single IP |
| `nmap scanme.nmap.org` | Domain |
| `nmap 192.168.10.0/24` | CIDR Subnet |
| `nmap 10.1.1.5-100` | IP Range |
| `nmap 10.1.1.3 10.1.1.6 10.1.1.8` | Multiple IPs |
| `nmap -iL targets.txt` | From file |
| `nmap -iR 10` | Random targets |
| `nmap --exclude 10.0.0.1` | Exclude host |
| `nmap --excludefile exclude.txt` | Exclude from file |

**Port Specification:**

| Command | Description |
|---------|-------------|
| `-p 80` | Single port |
| `-p 20-25` | Port range |
| `-p 80,443,8080` | Multiple ports |
| `-p-` | All 65535 ports |
| `-F` | Top 100 ports (fast) |
| `--top-ports 1000` | Top N ports |
| `-p U:53,T:22` | Protocol-specific |
| `-r` | Sequential (not randomized) |

---

### 27.2 Scan Methods Comparison

| Scan | Option | Root | Speed | Stealth | Accuracy |
|------|--------|------|-------|---------|----------|
| SYN | `-sS` | Yes | Fast | Medium | High |
| Connect | `-sT` | No | Slow | Low | High |
| UDP | `-sU` | Yes | Slow | Medium | Medium |
| FIN | `-sF` | Yes | Fast | High | Medium |
| NULL | `-sN` | Yes | Fast | High | Medium |
| Xmas | `-sX` | Yes | Fast | High | Medium |
| ACK | `-sA` | Yes | Fast | High | Firewall only |
| Window | `-sW` | Yes | Fast | Medium | Low |
| Maimon | `-sM` | Yes | Fast | High | Low |
| Idle | `-sI` | Yes | Slow | Very High | High |
| IP Proto | `-sO` | Yes | Medium | Low | High |

---

### 27.3 NSE Script Categories

| Category | Purpose | Example |
|----------|---------|---------|
| `safe` | No harm to target | http-title |
| `default` | -sC equivalent | (many) |
| `discovery` | Information gathering | dns-brute |
| `version` | Enhanced version detection | (with -sV) |
| `vuln` | Vulnerability detection | smb-vuln-ms17-010 |
| `auth` | Authentication checks | ftp-anon |
| `brute` | Credential testing | ssh-brute |
| `broadcast` | Network broadcast | broadcast-dns-sd |
| `dos` | Denial of service | http-slowloris |
| `exploit` | Active exploitation | (use caution) |
| `external` | External services | ip-geolocation-* |
| `intrusive` | May crash target | (various) |
| `malware` | Malware detection | http-google-malware |

---

### 27.4 Timing Templates

| Template | scan-delay | max-rtt-timeout | max-retries | Use Case |
|----------|-----------|-----------------|-------------|----------|
| T0 | 5 min | 5 min | 10 | Extreme stealth |
| T1 | 15 sec | 15 sec | 10 | Stealth |
| T2 | 400ms | 10 sec | 10 | Low bandwidth |
| T3 | 0ms | 10 sec | 10 | Default |
| T4 | 0-10ms | 1250ms | 6 | Fast accurate |
| T5 | 0-5ms | 300ms | 2 | Maximum speed |

---

### 27.5 Output Options

| Flag | Format | Best For |
|------|--------|----------|
| `-oN file` | Normal text | Human reading |
| `-oX file` | XML | Parsing, HTML reports |
| `-oG file` | Grepable | awk/grep filtering |
| `-oA prefix` | All three | Comprehensive |
| `-oS file` | Script Kiddie | Fun/leet-speak |

### 27.6 Verbosity & Debugging

| Option | Level |
|--------|-------|
| (none) | Normal |
| `-v` | Verbose |
| `-vv` | Very verbose |
| `-d` | Debug level 1 |
| `-d2` | Debug level 2 |
| `--packet-trace` | All packets |

---

## အခန်း ၂၈ — Appendices

### Appendix A: Common Port Numbers

| Port | Protocol | Service |
|------|----------|---------|
| 21 | TCP | FTP |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP/UDP | DNS |
| 67 | UDP | DHCP (server) |
| 68 | UDP | DHCP (client) |
| 69 | UDP | TFTP |
| 80 | TCP | HTTP |
| 88 | TCP/UDP | Kerberos |
| 110 | TCP | POP3 |
| 111 | TCP/UDP | RPC Portmapper |
| 123 | UDP | NTP |
| 135 | TCP | MS RPC |
| 137 | UDP | NetBIOS Name |
| 139 | TCP | NetBIOS Session |
| 143 | TCP | IMAP |
| 161 | UDP | SNMP |
| 389 | TCP/UDP | LDAP |
| 443 | TCP | HTTPS |
| 445 | TCP | SMB/CIFS |
| 465 | TCP | SMTPS |
| 514 | UDP | Syslog |
| 587 | TCP | SMTP Submission |
| 636 | TCP | LDAPS |
| 993 | TCP | IMAPS |
| 995 | TCP | POP3S |
| 1433 | TCP | MS SQL Server |
| 1521 | TCP | Oracle DB |
| 3306 | TCP | MySQL |
| 3389 | TCP | RDP |
| 5432 | TCP | PostgreSQL |
| 5900 | TCP | VNC |
| 6379 | TCP | Redis |
| 8080 | TCP | HTTP Proxy |
| 8443 | TCP | HTTPS Alt |
| 27017 | TCP | MongoDB |

---

### Appendix B: TCP Flags Reference

| Flag | Bit | Name | Description |
|------|-----|------|-------------|
| SYN | 0x02 | Synchronize | Initiate connection |
| ACK | 0x10 | Acknowledgment | Acknowledge data |
| RST | 0x04 | Reset | Abort connection |
| FIN | 0x01 | Finish | Graceful close |
| PSH | 0x08 | Push | Immediate data delivery |
| URG | 0x20 | Urgent | Urgent pointer valid |

**Common Flag Combinations:**

| Combination | Used In |
|-------------|---------|
| SYN | SYN Scan (-sS) |
| SYN+ACK | Three-Way Handshake response |
| FIN+PSH+URG | Xmas Scan (-sX) |
| FIN | FIN Scan (-sF) |
| ACK | ACK Scan (-sA) |
| FIN+ACK | Maimon Scan (-sM) |
| None (0) | NULL Scan (-sN) |

---

### Appendix C: ICMP Types and Codes

| Type | Name | Nmap Usage |
|------|------|------------|
| 0 | Echo Reply | Ping sweep response |
| 3 | Destination Unreachable | |
| 3:0 | Network Unreachable | |
| 3:1 | Host Unreachable | |
| 3:3 | Port Unreachable | UDP scan: closed port |
| 3:9 | Network Administratively Prohibited | |
| 3:10 | Host Administratively Prohibited | |
| 3:13 | Communication Administratively Prohibited | |
| 8 | Echo Request | Ping sweep probe |
| 13 | Timestamp Request | Timestamp ping (-PP) |
| 14 | Timestamp Reply | Timestamp ping response |
| 17 | Address Mask Request | Netmask ping (-PM) |

---

### Appendix D: Nmap Data Files Reference

| File | Path | Content |
|------|------|---------|
| `nmap-services` | `/usr/share/nmap/` | Port-to-service mapping, frequency |
| `nmap-service-probes` | `/usr/share/nmap/` | Version detection probes |
| `nmap-os-db` | `/usr/share/nmap/` | OS fingerprint database |
| `nmap-mac-prefixes` | `/usr/share/nmap/` | MAC vendor prefixes |
| `nmap-protocols` | `/usr/share/nmap/` | IP protocol numbers |
| `nmap-rpc` | `/usr/share/nmap/` | SunRPC program numbers |
| `scripts/` | `/usr/share/nmap/scripts/` | NSE scripts directory |
| `script.db` | `/usr/share/nmap/scripts/` | Script database index |

---

### Appendix E: Glossary of Terms

| Term | Definition |
|------|------------|
| **ARP** | Address Resolution Protocol — IP to MAC mapping |
| **Banner** | Greeting message from a service upon connection |
| **CIDR** | Classless Inter-Domain Routing — subnet notation (/24) |
| **CPE** | Common Platform Enumeration — standardized naming |
| **CVE** | Common Vulnerabilities and Exposures — vulnerability ID |
| **CVSS** | Common Vulnerability Scoring System — severity score |
| **DNS** | Domain Name System |
| **DTD** | Document Type Definition — XML schema |
| **Fingerprinting** | Identifying OS/service via network behavior |
| **Firewall** | Network security device that filters traffic |
| **IDS** | Intrusion Detection System |
| **IPS** | Intrusion Prevention System |
| **NSE** | Nmap Scripting Engine |
| **Ndiff** | Nmap scan comparison tool |
| **Ncat** | Nmap's networking utility |
| **Nping** | Nmap's packet generation tool |
| **Payload** | Actual data portion of a packet |
| **Probe** | Test packet sent to target |
| **Raw Socket** | Direct packet creation bypassing OS TCP stack |
| **RTT** | Round Trip Time — packet travel time |
| **Three-Way Handshake** | TCP connection establishment (SYN-SYN/ACK-ACK) |
| **WAF** | Web Application Firewall |

---

### Appendix F: Bibliography and Further Reading

1. **Nmap Network Scanning** — Gordon "Fyodor" Lyon, Official Nmap Project Guide, ISBN 978-0-9799587-1-7
2. **Nmap Reference Guide** — https://nmap.org/book/man.html
3. **Nmap Documentation Portal** — https://nmap.org/docs.html
4. **NSE Documentation Portal** — https://nmap.org/nsedoc/
5. **Nmap Changelog** — https://nmap.org/changelog.html
6. **TCP/IP Illustrated, Volume 1** — W. Richard Stevens
7. **Nmap 6: Network Exploration and Security Auditing Cookbook** — Paulino Calderón Pale
8. **Mastering the Nmap Scripting Engine** — Paulino Calderón Pale
9. **Secrets of Network Cartography** — James Messer
10. **Nmap in the Enterprise** — Angela Orebaugh, Becky Pinkard

---

## နိဂုံး (Conclusion)

ဤ **Nmap Mastery: From Beginner to Advanced (Myanmar Edition)** စာအုပ်သည် Nmap Security Scanner ၏ အခြေခံမှ Expert Level အထိ ပြည့်ပြည့်စုံစုံ လေ့လာနိုင်ရန် ရေးသားထားပါသည်။

စာအုပ်တွင်:
- **အခန်း ၂၈ ခန်း** — TCP/IP Fundamentals မှ Automation အထိ
- **Command 200+** — Breakdown, ရှင်းလင်းချက်, Example အပြည့်အစုံ
- **Tables & Comparisons** — Scan Types, Options, Performance
- **Practical Labs** — Beginner, Intermediate, Advanced, Expert
- **Real-World Scenarios** — Penetration Testing Workflows
- **Cheat Sheets** — Quick Reference for Daily Use

**အရေးအကြီးဆုံး သတိပေးချက်:** Nmap ကို ခွင့်ပြုချက်ရှိသော System များနှင့် Network များတွင်သာ အသုံးပြုပါ။ Ethical Hacking သည် တရားဝင်ခွင့်ပြုချက်ဖြင့်သာ ဆောင်ရွက်ရသော လုပ်ငန်းဖြစ်သည်။

**Practice on:** `scanme.nmap.org` — Nmap မှ ပညာရေးရည်ရွယ်ချက်အတွက် ထားရှိသော Test Server

---

> **ဤစာအုပ်သည် Official Nmap Documentation, Nmap Network Scanning (Official Book), Nmap Reference Guide, NSE Documentation နှင့် ယုံကြည်ရသော အခြားရင်းမြစ်များမှ ကိုးကားထားပါသည်။**

> **ဘာသာပြန်/ပြင်ဆင်မှု:** Myanmar (Burmese) Edition — 2026
