# 🛡️ Project: Command Injection Execution
## Vulnerability Exploitation and Defense (DVWA)

This project documents the identification and exploitation of an operating system (OS) command injection vulnerability within a deliberately vulnerable web application (DVWA). [cite_start]The goal was to demonstrate how lack of input sanitization allows an attacker to execute arbitrary system commands on the server and to detail necessary mitigation strategies. [cite: 3, 4, 5]

---

### 🎯 Objectives & Methodology

* [cite_start]**Objective:** To achieve remote command execution on a target server by abusing a web application feature that executes system commands based on user input (the "Ping for FREE" utility). [cite: 4, 5]
* [cite_start]**Methodology:** Utilized common command delimiters (`;`, `&&`, `|`) to break out of the intended command structure and inject new system calls. [cite: 7]

### 💡 Key Findings and Exploitation Steps

* [cite_start]**Vulnerability:** The web application fails to properly sanitize user input provided for an IP address in the "Ping for FREE" function. [cite: 4]
* [cite_start]**Successful Execution:** Initial test using the payload `127.0.0.1; whoami` successfully executed the `whoami` command and returned the server's running user, **`www-data`**, confirming command execution. [cite: 6, 114]
* [cite_start]**System Enumeration:** Successfully ran additional commands, such as `ls`, to list files on the server, demonstrating deeper system access. [cite: 8]
* [cite_start]**Bypass & Encoding:** Explored multiple delimiters (`&&`, `|`, and `&`) to validate bypass methods. [cite: 7] [cite_start]Used Burp Suite Repeater to send URL-encoded payloads (e.g., `127.0.0.1%26%26id`) to simulate a real-world, intercepted HTTP attack scenario. [cite: 9, 10]

### 🛠️ Tools & Technologies

* [cite_start]**Vulnerable Application:** Damn Vulnerable Web Application (DVWA) [cite: 2]
* [cite_start]**Proxy/Interception:** Burp Suite Repeater [cite: 9]
* **Operating System:** Kali Linux (for testing)

### 🔒 Mitigation Strategies (Defense Focus)

* **Input Sanitization:** Implement strict filtering or validation to ensure user input contains only expected characters (e.g., numbers and dots for an IP address) and neutralize or remove command delimiters (`&`, `|`, `;`, etc.).
* [cite_start]**Principle of Least Privilege:** Ensure the web server process (e.g., the `www-data` user found during the test [cite: 6]) runs with the absolute minimum privileges required, limiting the damage an attacker can do to the underlying OS.
* **Use of APIs:** Whenever possible, use built-in safe APIs (like language-specific functions for pinging) instead of directly executing external OS commands based on user input.

### 📜 Full Report and Deliverables

The complete penetration test report, including detailed screenshots of successful command executions and Burp Suite Repeater payloads, is available in the following PDF file:

* [P2.pdf (Full Command Injection Report)](./P2.pdf) 
    *(Note: You will replace this with the actual link once uploaded to GitHub)*

---