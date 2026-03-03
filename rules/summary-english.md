# Rules Summary Guide (English)

## Introduction
This is a summary guide for the project's `rules/` folder. This directory contains 119 files designed to detect a wide range of cyberattacks.

## Core Functionality
Snort rule files are collections of "Signatures." Each individual rule identifies a specific attack pattern or network behavior.

## Categorized Index
| Category | Location | Description |
| :--- | :--- | :--- |
| **2026 Latest** | `rules_2026/` | Newly discovered 2026 vulnerabilities (CVE-2026-X). |
| **Malware** | `rules/malware-*` | Detects Botnet and Backdoor communications. |
| **Web Attacks** | `rules/web-*` | Prevents SQL Injection and Cross-site Scripting. |
| **OS Security** | `rules/os-*` | Protects against Windows and Linux kernel exploits. |

## Technical Examples
- **Rule Example**: `alert tcp any any -> any 80 (msg:"SQL Injection attempt"; content:"UNION SELECT"; ...)`

## Summary
By deploying these rule sets, administrators can monitor entire network segments and identify malicious activity in real-time.
