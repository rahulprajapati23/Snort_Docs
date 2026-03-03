# Snort/Suricata Sensitive Data Rules Explanation

Yeh file `sensitive-data.rules` mein maujood network security rules ka detailed explanation hai. In rules ka main kaam network traffic mein sensitive information (jaise credit card, SSN, etc.) ko detect karna aur alert generate karna hai.

## Table of Contents
1. [General Structure](#general-structure)
2. [Rule Parameters](#rule-parameters)
3. [Detailed Rule Analysis](#detailed-rule-analysis)
    - [Credit Card Numbers](#1-credit-card-numbers)
    - [U.S. Social Security Numbers (SSN)](#2-us-social-security-numbers-ssn)
    - [Email Addresses](#3-email-addresses)
    - [U.S. Phone Numbers](#4-us-phone-numbers)

---

## General Structure
Har rule ka ek standard format hota hai:
`[Action] [Protocol] [Source IP] [Source Port] -> [Destination IP] [Destination Port] (Options)`

Saari rules mein common values:
- **Action**: `alert` (Jab rule match hogi, system alert message generate karega).
- **Protocol**: `tcp` (Transmission Control Protocol traffic ko monitor karta hai).
- **Source**: `$HOME_NET any` (Apne internal network se kisi bhi port se data ja raha ho).
- **Destination**: `$EXTERNAL_NET [80,20,25,143,110]` (Bahari network ke specific ports jaise HTTP, FTP, SMTP, IMAP, POP3 par).

---

## Rule Parameters
- **msg**: Alert ka message jo security logs mein dikhega.
- **metadata**: Yeh information ke liye hai (e.g., kaunsi services monitor ho rahi hain).
- **sd_pattern**: Yeh "Sensitive Data" preprocessor ka hissa hai jo patterns dhoondhta hai.
- **classtype**: `sdf` (Sensitive Data Framework).
- **sid (Signature ID)**: Har rule ki unique identity.
- **gid (Generator ID)**: `138` (Sensitive Data preprocessor ka ID).
- **rev**: Revision number (rule ka version).

---

## Detailed Rule Analysis

### 1. Credit Card Numbers
```snort
alert tcp $HOME_NET any -> $EXTERNAL_NET [80,20,25,143,110] (msg:"SENSITIVE-DATA Credit Card Numbers"; ... sd_pattern:2,credit_card; ...)
```
- **Kaam**: Yeh rule credit card numbers ko detect karti hai.
- **sd_pattern:2,credit_card**: `2` ka matlab hai ki agar packet mein 2 ya usse zyada credit card numbers milte hain, toh alert trigger hoga.

### 2. U.S. Social Security Numbers (SSN)
File mein SSN ke do types hain:
- **With Dashes**: `sd_pattern:2,us_social` (Agar 2 ya zyada dash wale SSN mile toh alert).
- **Without Dashes**: Yeh rule file mein commented hai (`#`). Iska sid:4 hai aur pattern `us_social_nodashes` hai.

### 3. Email Addresses
```snort
sd_pattern:20,email;
```
- **Kaam**: Network traffic mein email addresses detect karna.
- **Threshold**: Jab ek hi packet/flow mein 20 ya usse zyada email addresses milenge, tab alert aayega.

### 4. U.S. Phone Numbers
```snort
sd_pattern:20,(\d{3}) ?\d{3}-\d{4};
```
- **Kaam**: US format ke phone numbers detect karna.
- **Regex**: `(\d{3}) ?\d{3}-\d{4}` (Jaise: 123 456-7890 ya 123456-7890).
- **Threshold**: 20 phone numbers milne par alert aayega.

---

## Conclusion
Yeh rules sensitive information ko network se bahar leak hone se rokne ke liye design ki gayi hain (DLP - Data Loss Prevention).
