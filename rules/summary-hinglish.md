# Rules Summary Guide (Hinglish)

## Introduction
Yeh project ki `rules/` folder ki summary hai. Isme 119 files hain jo alag-alag kism ke hacking attacks ko detect karti hain.

## Core Functionality
Snort rules files "Signatures" ka collection hoti hain. Har rule ek specific attack pattern ko identify karne ka kaam karta hai.

## Categorized Index
| Category | Folder/File | Description |
| :--- | :--- | :--- |
| **2026 Latest** | `rules_2026/` | Nayi 2026 vulnerabilities (CVE-2026-X). |
| **Malware** | `rules/malware-*` | Botnets aur Backdoors ki communication. |
| **Web Attacks** | `rules/web-*` | SQL Injection aur Cross-site Scripting. |
| **OS Security** | `rules/os-*` | Windows aur Linux kernel exploits. |

## Technical Examples
- **Rule Example**: `alert tcp any any -> any 80 (msg:"SQL Injection attempt"; content:"UNION SELECT"; ...)` 

## Summary
In rules ko use karke hum pure network ki activity monitor kar sakte hain aur attacks ko real-time mein pehchan sakte hain.
