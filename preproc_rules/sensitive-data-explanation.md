# Sensitive Data Rules Explanation (Hinglish & English)

## 🇮🇳 Hinglish Explanation (Original Version)

Yeh file `sensitive-data.rules` ki details cover karti hai. Iska main maqsad PII (Personally Identifiable Information) ko leak hone se bachana hai.

### 💳 Sensitive Data Detection Kya Hai?
Is preprocessor (SDF) ka use karke hum Credit Card numbers, Social Security Numbers (SSN), Email Addresses, aur Phone numbers ko network traffic mein detect karte hain. Yeh "Data Loss Prevention (DLP)" ke liye use hota hai.

| Type | GID | Alert Message |
| :--- | :--- | :--- |
| **Credit Card** | 138 | `SDF_COMBO_ALERT`: Multiple sensitive fields found. |
| **Email** | 138 | `SDF_EMAIL_ADDRESS`: Email leaks detected in plain text. |
| **SSN** | 138 | `SDF_SOCIAL_SECURITY_NUMBER`: SSN patterns found in traffic. |

---

## 🇬🇧 Simple English Explanation (New Version)

This document provides details for `sensitive-data.rules`. Its primary goal is to prevent the leakage of Personally Identifiable Information (PII).

### 💳 What is Sensitive Data Detection?
Using the Sensitive Data Filtering (SDF) preprocessor, we can monitor network traffic for patterns like Credit Card numbers, Social Security Numbers (SSN), Email addresses, and Phone numbers. This is a core part of "Data Loss Prevention (DLP)".

| Type | GID | Alert Message |
| :--- | :--- | :--- |
| **Credit Card** | 138 | `SDF_COMBO_ALERT`: Multiple sensitive data fields detected. |
| **Email** | 138 | `SDF_EMAIL_ADDRESS`: Email addresses found in unencrypted traffic. |
| **SSN** | 138 | `SDF_SOCIAL_SECURITY_NUMBER`: SSN patterns identified in the data stream. |

---

## 📝 Usage Note
Bilingual documentation helps in quick review for university exams (SEM_06) and professional reports.
Yeh documentation exams aur professional reports dono ke liye useful hai.
