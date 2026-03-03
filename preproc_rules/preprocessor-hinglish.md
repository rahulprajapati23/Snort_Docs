# Snort Preprocessor Rules Explanation (Hinglish)

## Introduction
Yeh file `preprocessor.rules` ke baare mein hai. Preprocessor ka kaam IDS engine ke rules check karne se pehle traffic ko "normalize" aur "clean" karna hota hai.

## Core Functionality
Snort preprocessors raw packet data ko process karte hain taaki attackers traffic ko obfuscate na kar saken.
- **Normalization**: Alag-alag formats ko ek standard format mein convert karna.
- **Anomaly Detection**: Packet headers mein protocol violations dhoondhna.

## Categorized Index
| Category | Purpose | Alerts |
| :--- | :--- | :--- |
| **HTTP Inspect** | Web traffic cleaning | GID 119: Malformed headers, Oversized chunks |
| **Stream5** | Session state management | GID 135: TCP segment overlapping/retransmits |
| **DCE/RPC** | RPC decoding | GID 130: Fragments and MS08-067 detection |

## Technical Examples
- **Example GID 119**: Agar attacker `..%2f..%2f` bhejta hai, toh preprocessor ise decode karke `../../` mein badal deta hai taaki rule ise pakad sake.

## Summary
Preprocessors network security ki pehli layer hain jo evasion attacks ko block karti hain.
