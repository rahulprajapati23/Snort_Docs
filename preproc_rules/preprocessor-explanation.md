# Snort Preprocessor Rules Explanation (Hinglish & English)

## 🇮🇳 Hinglish Explanation (Original Version)

Yeh file `preprocessor.rules` ka detail hai. Preprocessor ka kaam IDS engine (standard rules) tak traffic pahunchne se pehle use "normalize" aur "clean" karna hota hai.

### 🔍 Preprocessor Kya Hai?
Preprocessor Snort ka woh "security guard" hai jo packet ke binary data ko rules check karne ke liye ready karta hai. Agar traffic malformed hai ya evasive (attack chhupane waali) hai, toh preprocessor vahi alert generate kar deta hai.

### 🛡️ Main Preprocessor Alerts
- **GID: 119, 122, 125, 129, etc.**
- **HTTP Inspect (GID 119)**:
    - `HTTP_OVERSZ_CHUNK_STACK`: Agar attacker boht badi chunks bhej ke buffer overflow karne ki koshish kare.
    - `HTTP_NON_RFC_CHAR`: HTTP signatures mein ajeeb characters dhoondhna.
- **Stream5 (GID 135)**:
    - `STREAM5_TCP_OVERLAP_DIFFERENT_DATA`: TCP Segmentation attack ko pakadna.
- **DCE/RPC (GID 130)**:
    - `DCERPC_MS08_067`: Famous Windows remote exploit ka detection.

---

## 🇬🇧 Simple English Explanation (New Version)

This document explains the functionality of `preprocessor.rules`. A preprocessor is responsible for "normalizing" and "cleaning" network traffic before it reaches the main detection engine.

### 🔍 What is a Preprocessor?
Think of a preprocessor as a "security guard" that prepares raw data for inspection. It identifies malformed packets or evasion techniques used by attackers to hide malicious activity.

### 🛡️ Key Preprocessor Alerts
- **GID: 119, 122, 125, 129, etc.**
- **HTTP Inspect (GID 119)**:
    - `HTTP_OVERSZ_CHUNK_STACK`: Prevents buffer overflow attacks caused by oversized data chunks.
    - `HTTP_NON_RFC_CHAR`: Detects invalid characters in HTTP requests.
- **Stream5 (GID 135)**:
    - `STREAM5_TCP_OVERLAP_DIFFERENT_DATA`: Detects TCP overlapping segmentation attacks used to bypass firewalls.
- **DCE/RPC (GID 130)**:
    - `DCERPC_MS08_067`: Detects historical but critical Windows remote code execution exploits.

---

## 📝 Summary / Conclusion
Dono languages mein yeh file aapko preprocessor ke roles aur unke specific alerts ko samajhne mein madad karegi.
Both versions help you understand the role of preprocessors in maintaining network hygiene.
