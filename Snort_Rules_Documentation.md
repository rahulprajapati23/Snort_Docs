# Snort Rules Documentation

This document provides a categorized overview of the Snort rule files located in the `rules/` directory. These rules are essential for detecting various types of network threats, from malware and browser exploits to protocol anomalies.

---

## 📂 Rule Categories

### 🖱️ Browser & Client Exploits
These rules target vulnerabilities in web browsers and common client-side applications.

- **browser-chrome.rules**: Detection for Google Chrome specific vulnerabilities.
- **browser-firefox.rules**: Detection for Mozilla Firefox specific vulnerabilities.
- **browser-ie.rules**: Extensive ruleset for Internet Explorer exploits.
- **browser-other.rules**: Rules for other browsers like Opera, etc.
- **browser-plugins.rules**: Targets vulnerabilities in browser plugins (Java, Flash, ActiveX).
- **browser-webkit.rules**: Detection for WebKit-based browsers (Safari, etc.).
- **file-flash.rules**: Rules for malicious Adobe Flash files.
- **file-java.rules**: Rules targeting Java-based exploits.
- **file-pdf.rules**: Detection for malicious PDF documents.
- **web-activex.rules**: Targets malicious ActiveX controls.
- **web-client.rules**: General client-side web application exploits.

---

### 🦠 Malware & Botnets
Rules dedicated to detecting Command & Control (C&C) traffic, backdoors, and known malware signatures.

- **backdoor.rules**: Detection for known backdoor communication patterns.
- **blacklist.rules**: Rules based on known malicious IP/host lists.
- **botnet-cnc.rules**: Identifies traffic related to botnet command and control.
- **indicator-compromise.rules**: Detects activity that strongly suggests a system is compromised.
- **malware-backdoor.rules**: Specific signatures for malware backdoors.
- **malware-cnc.rules**: High-fidelity signatures for malware C2 servers.
- **malware-other.rules**: General malware signatures that don't fit other categories.
- **malware-tools.rules**: Detection for hacking tools used by malware.
- **spyware-put.rules**: Detects spyware that "puts" or uploads sensitive data.
- **virus.rules**: Signatures for traditional computer viruses.

---

### 🕸️ Web & Server Attacks
Protects web servers and application layers from common attacks like SQL Injection and XSS.

- **server-apache.rules**: Specific rules for Apache HTTP Server.
- **server-iis.rules**: Specific rules for Microsoft IIS servers.
- **server-mail.rules**: Rules for securing mail servers (SMTP, POP3, IMAP).
- **server-mssql.rules / server-mysql.rules / server-oracle.rules**: Database-specific attack detection.
- **server-webapp.rules**: General web application vulnerability detection.
- **sql.rules**: Detection for SQL Injection attacks across various platforms.
- **web-attacks.rules**: Generic web-based attack patterns.
- **web-cgi.rules**: Detection for old-school CGI script exploits.
- **web-php.rules**: Targets PHP-specific vulnerabilities.

---

### 🛰️ Protocol Anomalies & Networking
Detects unusual behavior in standard network protocols.

- **bad-traffic.rules**: Detection for malformed packets and invalid protocol headers.
- **dns.rules / protocol-dns.rules**: Monitoring for DNS-based attacks and anomalies.
- **ftp.rules / protocol-ftp.rules**: Rules for FTP protocol security.
- **icmp.rules / icmp-info.rules**: Monitoring ICMP (ping) traffic for reconnaissance or tunneling.
- **protocol-imap.rules / protocol-pop.rules / protocol-snmp.rules**: Security rules for specific application-layer protocols.
- **protocol-voip.rules / voip.rules**: Dedicated rules for Voice over IP security (SIP, etc.).
- **telnet.rules / protocol-telnet.rules**: Securing unencrypted remote shell access.

---

### 🛡️ OS & Infrastructure
Targeting vulnerabilities in specific Operating Systems.

- **os-linux.rules**: Linux-specific vulnerability detection.
- **os-windows.rules**: Extensive rules for Windows OS vulnerabilities.
- **os-mobile.rules**: Protection for mobile operating systems (Android, iOS).
- **scada.rules / protocol-scada.rules**: Rules for protecting Industrial Control Systems (ICS/SCADA).

---

### 🔍 Indicators of Reconnaissance
Detects tools and patterns used by attackers to scan and probe networks.

- **indicator-scan.rules**: Detects scanning tools like Nmap, Nessus, etc.
- **scan.rules**: General reconnaissance and port scanning detection.
- **finger.rules**: Old protocol often used for user enumeration.

---

### 📄 File-Based Analysis
Rules that inspect specific file types for malicious content.

- **file-executable.rules**: Detection for malicious executables (PE, ELF).
- **file-image.rules**: Rules for malicious image files (JPEG, PNG, etc.).
- **file-office.rules**: Signatures for malicious Microsoft Office documents.
- **file-multimedia.rules**: Rules for audio/video file exploits.
- **file-identify.rules**: Used by Snort to identify file types for further inspection.

---

### 🛠️ Local & Miscellaneous
- **local.rules**: This is where you should add your custom, user-defined rules.
- **experimental.rules**: New or unstable rules currently under testing.
- **policy.rules**: General corporate policy enforcement (e.g., unauthorized software).
- **pua-adware.rules / pua-other.rules**: Potentially Unwanted Applications and Adware detection.

---

> [!TIP]
> Always keep your `local.rules` clean and documented. If you add a new rule, try to follow the same categorization naming convention used in this directory.
