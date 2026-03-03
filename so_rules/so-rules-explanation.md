# Shared Object Rules Explanation (Bilingual)

## 🇮🇳 Hinglish Explanation (Original Version)

Yeh `so_rules/` folder ka explanation hai. Standard rules text files hoti hain, lekin Shared Object (SO) rules compiled binary rules hoti hain.

### ⚙️ Shared Object (SO) Rules Kya Hain?
SO rules C language mein likhi jati hain aur compiled binaries (.so files) ki tarah IDS mein load hoti hain. Yeh un attacks ko detect karne ke liye zaruri hain jo boht complex hote hain aur jinne simple text-based rules se detect karna mushkil hota hai.

- **Accuracy**: compiled hone ki wajah se yeh rules fast aur zyada accurate hoti hain.
- **Stub Rules**: Is folder mein aapko text files (`.rules`) dikhengi jo SO stubs hain, jo compiled modules ko call karti hain.

---

## 🇬🇧 Simple English Explanation (New Version)

This document explains the contents of the `so_rules/` folder. While standard rules are simple text files, Shared Object (SO) rules are compiled binary rules.

### ⚙️ What are Shared Object (SO) Rules?
SO rules are written in the C language and loaded into the IDS as compiled binaries (.so files). They are essential for detecting complex vulnerabilities and multi-stage attacks that are difficult to identify using simple text-based rules.

- **Accuracy & Speed**: Because they are compiled, these rules are generally faster and provide higher detection accuracy.
- **Stub Rules**: The `.rules` files in this directory are "stubs" that link the IDS to the actual compiled binary modules.

---

## 🔥 Key Categories in SO Rules
- **Browser-IE**: Complex Internet Explorer memory corruption rules.
- **Server-WebApp**: Advanced web application exploit detection.
- **Malware-CNC**: Precise callbacks for sophisticated malware.
