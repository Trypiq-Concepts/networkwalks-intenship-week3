<div align="center">

# 🔑 Credential Auditing JTR

**Mastering offline hash extraction, dictionary attacks, and credential security assessments**
</div>

<p align="center">
<img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
<img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
<img src="https://img.shields.io/badge/Tool-John%20the%20Ripper-0070C0?style=flat-square&labelColor=000000" />
<img src="https://img.shields.io/badge/Skill-Dictionary%20Attack-404040?style=flat-square&labelColor=C00000" />
<img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=000000" />
<img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
<img src="https://img.shields.io/badge/David%20Ishaya-CC0000?style=flat-square" />
</p>

---

## 📌 Project Overview

This project documents the practical labs completed during Week 3 of the Networkwalks Cybersecurity Internship, focusing on **password cracking and cryptographic analysis**. 

The modules explore how password-protected files secure sensitive information, how hashes are extracted using parsing utilities, and how dictionary attacks expose the risks associated with weak user credentials.

---
## 📥 Practice File: 

You can download the sample locked PDF directly from this repository: [Download My Locked PDF1.pdf], [Download My Locked PDF2.pdf], [Download My Locked PDF3.pdf] and [Download My Locked PDF3.pdf]

---

---

## 🎯 Objectives

The main goals of these lab modules are:
- Understand the fundamental differences between **encryption** (two-way) and **hashing** (one-way cryptographic functions).
- Perform native command-line hash extraction using Perl scripts (`pdf2john.pl`) on Kali Linux
- Execute offline dictionary attacks using **John the Ripper** and manage local session potfiles (`john.pot`).
- Utilize browser-based web utility tools (**Networkwalks Hash Calculator** and **Password Cracker**) for rapid credential analysis.
- Analyze why offline cracking is effective against local files, contrasted with the limitations imposed by server-side rate-limiting on live web applications.

---

## 🛠️ Lab Specifications & Tools Used

| Component / Tool | Purpose / Function |
| :--- | :--- |
| **Kali Linux** | Primary security workstation and terminal environment |
| **John the Ripper** | Advanced offline password-cracking and hash-analysis tool |
| **`pdf2john.pl` (Perl)** | Script to parse encrypted PDF file headers and extract crackable hashes |
| **Networkwalks Web Utilities** | Browser-based Hash Calculator and Dictionary Cracker tools |

---

## 📂 Lab Tasks & Execution Procedure

### **Module 1: Kali Linux Terminal Workflow**
1. **Hash Extraction:** Located and executed the Perl script to extract the encryption hash from the locked PDF file into a local text file:
   ```bash
   perl /usr/share/john/pdf2john.pl "My Locked PDF1.pdf" > hash.txt
   ```
2. **Password Cracking:** Executed John the Ripper against the extracted hash using default dictionaries:
   ```bash
   john hash.txt
     ```
3. **Result Verification:** Successfully recovered the plaintext password and utilized the `--show` flag to retrieve results from the local potfile.

### **Module 2: Browser-Based Utility Workflow (Networkwalks Tools)**
1. **Accessing Hash Calculator:** Opened the [Networkwalks Hash Calculator](https://networkwalks.com/hash-calculator/) tool directly in the web browser.
2. **Hash Extraction:** Uploaded the encrypted `My Locked PDF1.pdf` file into the browser utility to locally parse the file and extract the complete `$pdf$` hash.
3. **Accessing Password Cracker:** Opened the [Networkwalks Password Cracker](https://networkwalks.com/password-cracker/) dictionary attack tool.
4. **Executing Attack & Verification:** Pasted the copied `$pdf$` hash into the cracker, selected the built-in wordlist (100 passwords), and ran the dictionary attack to successfully uncover the plaintext password.

---

## 🐞 Key Technical Insights & Troubleshooting

- **Potfile Management (`john.pot`):** Once John the Ripper successfully cracks a hash, it stores the result in a local history file.

Subsequent attempts to run `john hash.txt` will result in a "No password hashes left to crack" prompt, requiring the `--show` flag (`john --show hash.txt`) to review previous recoveries.

---

## 💡 What I Learned

1. **Cryptographic Foundations:** Gained deep clarity on how hashing algorithms generate un-reversible digital fingerprints for verification.
2. **Command-Line Proficiency:** Mastered file parsing with Perl helper scripts and automated dictionary iteration with John the Ripper.
3. **Alternative Workflows:** Explored client-side browser utilities for rapid hash extraction and analysis without installation overhead.

---

## 👤 Author

**David Ishaya**   

---
