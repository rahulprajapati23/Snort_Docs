# Sensitive Data Rules Explanation (English)

## Introduction
This documentation covers the `sensitive-data.rules`. Its primary purpose is to protect Personally Identifiable Information (PII) from being leaked across the network.

## Core Functionality
The Sensitive Data Filter (SDF) scans outgoing and incoming traffic for specific patterns such as credit card numbers or SSNs.
- **Pattern Matching**: Using regular expressions and predefined algorithms to find sensitive data.
- **DLP Implementation**: Acts as a "Data Loss Prevention" tool within the IDS.

## Categorized Index
| Data Type | Purpose | Alert Example |
| :--- | :--- | :--- |
| **Credit Card** | Protects financial data | GID 138: `SDF_COMBO_ALERT` |
| **Email** | Ensures data privacy | GID 138: `SDF_EMAIL_ADDRESS` |
| **SSN** | Prevents identity theft | GID 138: `SDF_SOCIAL_SECURITY_NUMBER` |

## Technical Examples
- **Alert Example**: If an unauthorized user tries to exfiltrate credit card numbers from a server, the SDF preprocessor will trigger an alert as the data packets pass through the IDS.

## Summary
Sensitive data rules are critical for organizations to safeguard their intellectual property and comply with data privacy regulations.
