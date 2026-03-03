# Sensitive Data Rules Explanation (Hinglish)

## Introduction
Yeh documentation `sensitive-data.rules` ke liye hai. Iska maqsad PII (Personally Identifiable Information) ko network se leak hone se bachana hai.

## Core Functionality
Sensitive Data Filter (SDF) traffic ko scan karta hai specified patterns (jaise CC numbers, SSN) ke liye. 
- **Pattern Matching**: Regex aur built-in patterns ka use karke sensitive data dhoondhna.
- **DLP Implementation**: Data Loss Prevention tool ki tarah kaam karta hai.

## Categorized Index
| Data Type | Purpose | Alert Example |
| :--- | :--- | :--- |
| **Credit Card** | Banking data protection | GID 138: `SDF_COMBO_ALERT` |
| **Email** | Communication privacy | GID 138: `SDF_EMAIL_ADDRESS` |
| **SSN** | Identity theft prevention | GID 138: `SDF_SOCIAL_SECURITY_NUMBER` |

## Technical Examples
- **Alert Example**: Agar koi attacker database se users ke credit card numbers extract kar raha hai, toh SDF vahi alert generate kar dega jab data packets pass honge.

## Summary
Sensitive data rules organizations ki intellectual property aur user data ko protect karti hain.
