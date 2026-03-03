# Shared Object Rules Guide (Hinglish)

## Introduction
Yeh file `so_rules/` folder ke baare mein hai. SO (Shared Object) rules compiled binary rules hoti hain jo complex attacks ke liye use hoti hain.

## Core Functionality
Shared Object rules normal rules se alag tarah se kaam karti hain.
- **Compiled Logic**: Yeh C code mein likhi jati hain aur executable library (.so/ .dll) ki tarah load hoti hain.
- **Complex Detection**: Inhe tab banaya jata hai jab attack simple pattern matching se detect nahi ho sakta.

## Categorized Index
| Module | Target | Reason |
| :--- | :--- | :--- |
| **Browser-IE** | Internet Explorer | Heap corruption aur Memory leaks. |
| **Protocol-DNS** | DNS traffic | Recursive query floods aur tunneling. |
| **Server-Mail** | Exchange/Mail | Complex SMTP buffer overflows. |

## Technical Examples
- **GID 3**: Shared Object rules ka Global ID 3 hota hai. Yeh detection engine ke internal logic ko call karti hain.

## Summary
SO rules advanced threats ke liye ek powerful tool hain jo high speed detection provide karti hain.
