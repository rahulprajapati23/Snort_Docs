# Shared Object Rules Guide (English)

## Introduction
This file explains the purpose and structure of the `so_rules/` folder. Shared Object (SO) rules are compiled binary rules used for identifying complex network attacks.

## Core Functionality
Shared Object rules function differently from standard text-based rules.
- **Compiled Logic**: They are written in the C language and loaded into the IDS as pre-compiled libraries (.so/ .dll).
- **Complex Detection**: They are developed for scenarios where attacks are too complex to be detected by simple text pattern matching.

## Categorized Index
| Module | Target | Usage |
| :--- | :--- | :--- |
| **Browser-IE** | Internet Explorer | Detects heap corruption and memory leaks. |
| **Protocol-DNS** | DNS traffic | Stops recursive query floods and data tunneling. |
| **Server-Mail** | Exchange/PostFix | Identifies advanced SMTP buffer overflows. |

## Technical Examples
- **GID 3**: Shared Object rules typically use GID 3. They interact directly with the internal detection engine's logic.

## Summary
SO rules are powerful tools designed for advanced threat detection, offering high-performance analysis for sophisticated exploits.
