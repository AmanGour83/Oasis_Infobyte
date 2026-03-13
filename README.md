# Oasis Infobyte — Security Analyst Internship <p align="right">by Aman Gour</p>


This repository contains all the tasks provided by Oasis Infobyte for the Security Analyst Internship program. Each task is organized with proper documentation and implementation to demonstrate practical skills in cybersecurity and security analysis.

---

## Intern Details

| Field        | Details                        |
|-------------|-------------------------------|
| Program      | Security Analyst Internship   |
| Organization | Oasis Infobyte                |
| Duration     | 1 Month                       |
| Lab Setup    | Kali Linux + Metasploitable 2 (VirtualBox) |

---

## Repository Structure

```
Oasis_Infobyte/
├── Task1_Nmap_Scan/
├── Task2_UFW_Firewall/
├── Task3_SQL_Injection_DVWA_Low/
├── Task4_Network_Security_Threats_Report/
├── Task5_Social_Engineering_Report/
├── Task6_Patch_Management_Report/
├── Task7_Nikto_Scan/
├── Task8_Wireshark/
├── Task9_SQL_Injection/
└── Task10_Security_Assessment/
```

---

## Tasks Overview

### ✅ Task 1 — Basic Network Scanning with Nmap
**Level:** Beginner | **Tool:** Nmap 7.98

Performed a network scan against Metasploitable 2 (192.168.56.101) using Nmap's service version detection flag (`-sV`). Identified 23 open TCP ports and documented the significance of each service including critical findings such as vsftpd 2.3.4 backdoor, exposed root bindshell, and legacy plaintext protocols.

**Key Files:**
- `nmap_scan_results.txt` — Raw Nmap output
- `README.md` — Detailed analysis of all 23 open ports
- `screenshots/` — Terminal screenshots

---

### ✅ Task 2 — Basic Firewall Configuration with UFW
**Level:** Beginner | **Tool:** UFW (Uncomplicated Firewall)

Configured a basic firewall on a Linux system using UFW to allow SSH traffic and deny HTTP traffic. Documented all firewall rules and verified the active configuration.

**Key Files:**
- `ufw_configuration.sh` — Firewall setup script
- `README.md` — Configuration explanation
- `screenshots/` — UFW status output

---

### ✅ Task 3 — SQL Injection on DVWA (Low Security)
**Level:** Beginner | **Tool:** DVWA, Browser

Demonstrated SQL Injection on DVWA set to low security level. Performed basic injection on the login and user input pages, captured output and explained the vulnerability.

**Key Files:**
- `sql_injection_exploit.sh` — Basic exploit script
- `README.md` — Attack walkthrough and explanation
- `screenshots/` — Step-by-step process screenshots

---

### ✅ Task 4 — Research Report: Common Network Security Threats
**Level:** Beginner | **Type:** Research Report

Wrote a comprehensive research report on common network security threats including DoS/DDoS attacks, Man-in-the-Middle (MITM) attacks, and IP spoofing. Each threat is explained with real-world examples, impact analysis, and mitigation strategies.

**Key Files:**
- `network_security_threats_report.md` — Full research report

---

### ✅ Task 5 — Research Report: Social Engineering Attacks
**Level:** Beginner | **Type:** Research Report

Researched and documented social engineering attack types including phishing, pretexting, baiting, and vishing. Includes real-world case studies, organizational impact analysis, and prevention recommendations.

**Key Files:**
- `social_engineering_report.md` — Full research report

---

### ✅ Task 6 — Research Report: Patch Management
**Level:** Beginner | **Type:** Research Report

Wrote a detailed report on the importance of patch management in cybersecurity. Covers consequences of unpatched systems, real-world breach examples caused by missing patches, and best practices for implementing an effective patch management strategy.

**Key Files:**
- `patch_management_report.md` — Full research report

---

### ✅ Task 7 — Vulnerability Scanning with Nikto
**Level:** Intermediate | **Tool:** Nikto v2.6.0

Performed a web vulnerability scan against DVWA on Metasploitable 2 (`http://10.0.2.3/dvwa/`) using Nikto. Identified 26 vulnerabilities including outdated Apache/PHP versions, missing security headers, insecure cookies, directory indexing, HTTP TRACE/XST, and PHP Easter Egg exposure.

**Key Files:**
- `nikto_scan_results.txt` — Raw Nikto output
- `README.md` — Full analysis of all 26 findings with mitigations
- `screenshots/` — Scan execution screenshots

---

### ✅ Task 8 — Capture Network Traffic with Wireshark
**Level:** Intermediate | **Tool:** Wireshark

Captured and analyzed 213 packets of live network traffic between Kali Linux (10.0.2.5) and Metasploitable 2 (10.0.2.3). Analysis covered TCP handshakes, plaintext HTTP credentials, POST request behavior, ARP table disclosure, DHCP lease renewal, TLS external traffic, and TCP session lifecycle.

**Key Files:**
- `wireshark_capture.pcap` — Raw packet capture
- `README.md` — Full packet-level analysis report
- `screenshots/` — Wireshark UI screenshots

---

### ✅ Task 9 — SQL Injection Exploit on DVWA (Advanced)
**Level:** Advanced | **Tool:** Browser-based manual SQLi

Performed a complete SQL Injection attack chain against DVWA on Metasploitable 2. Escalated from basic enumeration through always-true bypass, UNION-based data extraction, MySQL version and database name disclosure, table enumeration, and full credential dump including MD5 password hashes for all 5 users.

**Payloads Used:**
- `1' OR '1'='1` — Dump all users
- `' UNION SELECT null, version()-- -` — Extract MySQL version (5.0.51a)
- `' UNION SELECT null, database()-- -` — Extract DB name (dvwa)
- `' UNION SELECT null, table_name FROM information_schema.tables WHERE table_schema=database()-- -` — Enumerate tables
- `' UNION SELECT user, password FROM users-- -` — Dump credentials

**Key Files:**
- `sql_injection_exploit.sh` — Full curl-based exploit script
- `README.md` — 6-phase attack documentation with remediation guide
- `screenshots/` — Step-by-step screenshots (7 images)

---

### ✅ Task 10 — Network Security Assessment Report
**Level:** Advanced | **Tools:** Nmap 7.98, Wireshark

Conducted a full network security assessment combining active Nmap scanning (port scan, service version, OS detection, vuln scripts) with Wireshark traffic analysis. Identified 18 vulnerabilities across 23 open ports including 9 critical severity findings with confirmed CVEs.

**Nmap Scans Performed:**
```bash
nmap 10.0.2.3 -oN nmap_results.txt
nmap -sV 10.0.2.3 >> nmap_results.txt
nmap -O 10.0.2.3 >> nmap_results.txt
nmap --script vuln 10.0.2.3 >> nmap_results.txt
```

**Critical CVEs Confirmed:**
- CVE-2011-2523 — vsftpd 2.3.4 backdoor (root RCE)
- CVE-2014-3566 — SSL POODLE
- CVE-2014-0224 — OpenSSL CCS Injection
- CVE-2015-4000 — Logjam TLS downgrade
- CVE-2007-6750 — Slowloris DoS

**Key Files:**
- `network_security_assessment.md` — Full 18-finding assessment report
- `nmap_results.txt` — All 4 Nmap scan outputs
- `wireshark_capture.pcap` — Network traffic capture
- `README.md` — Task summary

---

## Tools Used

| Tool       | Version  | Purpose                          |
|-----------|---------|----------------------------------|
| Nmap       | 7.98    | Port scanning & vuln detection   |
| Nikto      | 2.6.0   | Web vulnerability scanning       |
| Wireshark  | —       | Network traffic capture/analysis |
| DVWA       | v1.0.7  | Target web application           |
| Metasploit 2 | —     | Vulnerable target machine        |
| Kali Linux | 2025.4  | Attacker machine                 |
| VirtualBox | —       | Lab virtualization               |

---

## Lab Environment

| Component      | Details                          |
|---------------|----------------------------------|
| Attacker       | Kali Linux 2025.4 (10.0.2.5)   |
| Target         | Metasploitable 2 (10.0.2.3)    |
| Network        | VirtualBox NAT Network           |
| Host-Only Net  | 192.168.56.0/24                 |

---

## Disclaimer

All tasks were performed in a controlled lab environment using intentionally vulnerable machines (Metasploitable 2 / DVWA) for educational purposes only as part of the Oasis Infobyte Security Analyst Internship. Performing any of these techniques on systems without explicit written authorization is illegal.
