# Snort/Suricata Decoder Rules Explanation

Yeh file `decoder.rules` ka detailed explanation hai. Decoder ka kaam packet ke sabse basic level (Header levels) par galatiyan ya anomalies dhoondhna hota hai.

## Table of Contents
1. [What is a Decoder?](#what-is-a-decoder)
2. [Core Decoding Anomalies](#core-decoding-anomalies)
    - [IPv4 & IPv6 Anomalies](#1-ipv4--ipv6-anomalies)
    - [TCP & UDP Header Issues](#2-tcp--udp-header-issues)
    - [ICMP Anomalies](#3-icmp-anomalies)
    - [Ethernet & VLAN Issues](#4-ethernet--vlan-issues)

---

## What is a Decoder?
Decoder IDS ka woh part hai jo packet ke binary data ko readable format mein convert karta hai. Agar packet header hi galat (malformed) hai, toh decoder alert generate karta hai.

---

## Core Decoding Anomalies

### 1. IPv4 & IPv6 Anomalies
- **GID: 116**
- **Alerts**:
    - `DECODE_IPV4_INVALID_HEADER_LEN`: Agar IP header ki length boht choti ya boht badi ho.
    - `DECODE_ZERO_TTL`: Time-to-Live zero hona suspicious hai (packet ko expire ho jana chahiye tha).
    - `DECODE_IPV6_BAD_NEXT_HEADER`: IPv6 header mein invalid extension header.

### 2. TCP & UDP Header Issues
- **TCP Alerts**:
    - `DECODE_TCP_SYN_FIN`: Jab SYN aur FIN flags ek saath set hon (Illegal state).
    - `DECODE_TCP_XMAS`: "Xmas Tree" scan jisme saare flags (FIN, PSH, URG) ON hote hain.
    - `DECODE_TCP_PORT_ZERO`: Source ya destination port 0 hona (illegal).
- **UDP Alerts**:
    - `DECODE_UDP_DGRAM_INVALID_LENGTH`: UDP packet ki length match na hona.

### 3. ICMP Anomalies
- **Alerts**:
    - `DECODE_ICMP_PING_NMAP`: Nmap scanner ka specific ICMP behavior.
    - `DECODE_ICMP_HDR_TRUNC`: truncated (adhura) ICMP header.

### 4. Ethernet & VLAN Issues
- **Alerts**:
    - `DECODE_BAD_VLAN`: Galat VLAN tagging jo security bypass karne ke liye use ho sakti hai.
    - `DECODE_ETH_HDR_TRUNC`: Ethernet header ka packet se chota hona.

---

## Summary
Decoder rules network ki "hygiene" maintain karti hain. Agar network par malformed (toote-foote) packets aa rahe hain, toh yeh unhe detect karke malware ya attackers ki koshishon ko pehchan leti hain.
