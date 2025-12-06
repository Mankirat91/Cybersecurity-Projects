
##  Information Gathering – Penetration Testing Report

This project focuses on gathering publicly available information about the target domain **vulnweb.com** using OSINT and reconnaissance techniques. The purpose of the assessment was to map the attack surface and identify potential entry points before exploitation.

###  Tools Used

* `nslookup`
* `whois`
* `dig`
* `amass`
* `Subfinder`
* `WhatWeb`
* `BuiltWith`
* `Gobuster / Dirb`
* `Nmap`
* `theHarvester`

### 🔍 Key Findings

| Area         | Summary                                                     |
| ------------ | ----------------------------------------------------------- |
| Domain Info  | Registered under **Gandi SAS** with DNSSEC unsigned         |
| Hosting      | Hosted on **AWS (Amazon Web Services)**                     |
| Subdomains   | **testphp.vulnweb.com** and others identified               |
| DNS Records  | A, NS, MX, TXT records enumerated                           |
| Technologies | Apache, PHP, analytics components detected                  |
| Directories  | Hidden directories discovered via brute-force               |
| Email OSINT  | No email leaks found                                        |
| Social OSINT | **Owned by Acunetix** (verified through LinkedIn & Twitter) |



---

### ✔ Status

## Information Gathering phase completed successfully.

###  Author

**Mankirat Singh**
Cybersecurity & Ethical Hacking
