# Snort Preprocessor Rules Explanation (English)

## Introduction
This file describes the purpose of the `preprocessor.rules`. Preprocessors work by "normalizing" and "cleaning" network traffic before it is sent to the main IDS detection engine.

## Core Functionality
Snort preprocessors process raw packet data to ensure that attackers cannot hide malicious activity using evasion techniques.
- **Normalization**: Converting various data formats into a standardized form.
- **Anomaly Detection**: Identifying protocol violations within packet headers.

## Categorized Index
| Category | Purpose | Alerts |
| :--- | :--- | :--- |
| **HTTP Inspect** | Web traffic normalization | GID 119: Malformed headers, Oversized data chunks |
| **Stream5** | TCP/UDP session tracking | GID 135: Overlapping TCP segments and retransmissions |
| **DCE/RPC** | Decoding RPC traffic | GID 130: Handling RPC fragments and detecting exploits |

## Technical Examples
- **Example GID 119**: If an attacker sends encoded strings like `..%2f..%2f`, the preprocessor decodes it to `../../` so the standard rules can detect the directory traversal attempt.

## Summary
Preprocessors serve as the first line of defense in network security, effectively blocking common evasion tactics used by hackers.
