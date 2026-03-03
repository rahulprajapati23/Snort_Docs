# Snort/Suricata Preprocessor Rules Explanation

Yeh file `preprocessor.rules` mein maujood rules ka explanation hai. Preprocessor ka kaam protocols ko deep level par analyze karna hota hai (jaise HTTP ka structure, Port scanning behavior, etc.).

## Table of Contents
1. [What is a Preprocessor?](#what-is-a-preprocessor)
2. [Key Preprocessors Analyzed](#key-preprocessors-analyzed)
    - [HTTP Inspect (HI)](#1-http-inspect-hi)
    - [Portscan Detection (PSNG)](#2-portscan-detection-psng)
    - [IP Fragmentation (FRAG3)](#3-ip-fragmentation-frag3)
    - [Stream5 (TCP Stream Reassembly)](#4-stream5-tcp-stream-reassembly)
    - [Application Protocols (SMTP, FTP, SSH)](#5-application-protocols-smtp-ftp-ssh)

---

## What is a Preprocessor?
Preprocessor packet sniffing ke baad aur detection engine se pehle kaam karta hai. Iska kaam fragmented packets ko jodna, encrypted traffic ko decode karna, aur protocol ki anomalies check karna hai taaki false alerts kam ho sakein.

---

## Key Preprocessors Analyzed

### 1. HTTP Inspect (HI)
- **GIDs: 119 (Client-side) & 120 (Server-side)**
- **Role**: Yeh HTTP traffic ko scan karta hai. 
- **Alerts**:
    - `HI_CLIENT_DOUBLE_DECODE`: Jab client double encoding ka use karke bypass ki koshish kare.
    - `HI_CLIENT_DIR_TRAV`: Directory traversal attack detection.
    - `HI_SERVER_JS_OBFUSCATION`: Jab server suspicious obfuscated JavaScript bhej raha ho.

### 2. Portscan Detection (PSNG)
- **GID: 122**
- **Role**: Yeh detect karta hai ki koi attackers aapke network ke ports scan toh nahi kar raha.
- **Alerts**:
    - `PSNG_TCP_PORTSCAN`: Seedha port scanning.
    - `PSNG_UDP_PORTSWEEP`: Ek hi host par multiple UDP ports check karna.
    - `PSNG_ICMP_PORTSWEEP`: ICMP (Ping) ka use karke live hosts dhoondhna.

### 3. IP Fragmentation (FRAG3)
- **GID: 123**
- **Role**: Attackers aksar bade packets ko tukdo (fragments) mein bhejte hain detection se bachne ke liye. Frag3 inko analyze karta hai.
- **Alerts**:
    - `FRAG3_TEARDROP`: Ek purana Dos attack jisme fragments overlap karte hain.
    - `FRAG3_SHORT_FRAG`: Bohat chote fragments jo suspicious hote hain.

### 4. Stream5 (TCP Stream Reassembly)
- **GID: 129**
- **Role**: TCP sessions ko track karna.
- **Alerts**:
    - `STREAM5_SESSION_HIJACKED`: Session hijacking ki koshish.
    - `STREAM5_DATA_ON_SYN`: SYN packet (connection start) ke saath data bhejna (invalid behavior).

### 5. Application Protocols (SMTP, FTP, SSH)
- **SMTP (GID 124)**: Email attacks like command overflow.
- **FTP (GID 125)**: File transfer attacks, bounce attacks.
- **SSH (GID 128)**: Secure shell attacks, version mismatch.

---

## Metadata and SID
- In rules mein `sid` (Signature ID) hamesha unique rehta hai lekin rules aksar complex patterns ke bajaye protocol logic par chalti hain.
- `classtype`: Rules ko categorize karta hai (e.g., `attempted-admin`, `protocol-command-decode`).
