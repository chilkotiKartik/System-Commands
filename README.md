<div align="center">

# ⚡ IIT Madras — BSSE2001: System Commands
### *The Next-Gen Interactive Learning Hub, Solved Practical Vault & Command-Line Masterclass*

<br/>

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=38BDF8&center=true&vCenter=true&width=700&height=50&lines=Master+Linux+CLI+%26+Bash+Scripting+%F0%9F%90%A7;IITM+BSSE2001+System+Commands+%E2%9A%A1;Interactive+Notes+%2B+Solved+Question+Vault+%F0%9F%93%9D;Unofficial+Open-Source+Learning+Initiative+%F0%9F%9A%80" alt="Typing SVG" />
</a>

<br/>

[![Community Learning](https://img.shields.io/badge/Initiative-Student_Driven_Learning-8B0000?style=for-the-badge&logo=open-access&logoColor=white)](#-disclaimer)
[![Course Focus](https://img.shields.io/badge/Course-BSSE2001-blue?style=for-the-badge&logo=gnubash&logoColor=white)](https://github.com/chilkotiKartik/System-Commands)
[![Linux](https://img.shields.io/badge/Linux-Terminal_Power-FCC624?style=for-the-badge&logo=linux&logoColor=black)](https://github.com/chilkotiKartik/System-Commands)
[![Bash](https://img.shields.io/badge/Bash-Scripting_Mastery-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)](https://github.com/chilkotiKartik/System-Commands)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

<br/>

[📢 Disclaimer](#-disclaimer--purpose) • [💡 Innovation & Vision](#-innovative-learning-philosophy) • [🗺️ Curriculum Roadmap](#-curriculum--weekly-roadmap) • [🚀 Week 01 Vault](#-week-01-deep-dive) • [⚡ Interactive Matrix](#-core-command-matrix)

---

</div>

> [!IMPORTANT]
> ### 📢 Disclaimer & Purpose
> **This is an independent, community-driven educational repository.**  
> It is **NOT** an official publication of, nor affiliated with or endorsed by **IIT Madras** or the **BS in Data Science & Applications Degree program**. All contents, interactive notes, diagrams, and problem breakdowns are created purely for **academic enhancement, peer collaboration, self-study, and open knowledge sharing**.

---

## 💡 Innovative Learning Philosophy

Traditional Linux documentation is dry and fragmented. This repository is built to revolutionize how students grasp Operating System mechanics:

```
   ┌─────────────────────────────────────────────────────────────┐
   │                  THE SYSTEM-COMMANDS ENGINE                 │
   └──────────────────────────────┬──────────────────────────────┘
                                  │
         ┌────────────────────────┼────────────────────────┐
         ▼                        ▼                        ▼
  🧠 Visual Mental Models   🎯 Exact Solved Qs       🧪 Terminal Sandbox
  (Inodes, Paths, Math)    (OPPE & Quiz Patterns)   (Hands-on experiments)
```

1. **Intuitive Mental Models:** No blind memorization. Understand octal math, inode mechanics, and file descriptor streams with crystal-clear visual breakdowns.
2. **OPPE & Quiz Ready:** Real exam-tested commands, edge-case analysis, and common trap warnings.
3. **Hyper-Modular Layout:** Every week is packaged as an isolated learning unit with indexable solutions, interactive experiments, and instant cheat sheets.

---

## 📁 Repository Blueprint

```
📁 System-Commands/
│
├── 📂 Week-01/                                          # Week 1: Linux & Bash Foundations
│   ├── 📄 README.md                                    # Week 1 Hub & Quick Index
│   ├── 📝 IITM_BSSE2001_Week1_Interactive_Notes.md     # In-depth concepts & commands
│   └── 🎯 IITM_BSSE2001_Week1_Bash_Practical_Questions_Solutions.md # Solved Qs & Tricks
│
├── 📂 Week-02/                                          # [Upcoming] Text Processing, RegEx, sed, awk
├── 📂 Week-03/                                          # [Upcoming] Shell Scripting & Control Structures
├── 📂 Week-04/                                          # [Upcoming] Process Control & Signals
├── 📂 Week-05/                                          # [Upcoming] Inodes, File Systems & Archives
└── 📄 README.md                                        # Master repository index
```

---

## 🗺️ Curriculum & Weekly Roadmap

| Week | Focus Topic | Notes | Practice & Solutions | Status |
| :---: | :--- | :---: | :---: | :---: |
| **01** | **Linux Architecture, Navigation, Wildcards & Permissions** | [📘 Notes](./Week-01/IITM_BSSE2001_Week1_Interactive_Notes.md) | [🎯 Solved Qs](./Week-01/IITM_BSSE2001_Week1_Bash_Practical_Questions_Solutions.md) | `✅ Completed` |
| **02** | Text Filters, Regex (`grep`, `sed`, `awk`, `cut`, `sort`) | — | — | `🔄 Upcoming` |
| **03** | Shell Scripting, Variables, Loops & Conditionals | — | — | `🔄 Upcoming` |
| **04** | Process Management, Signals & Job Control (`kill`, `ps`, `cron`) | — | — | `🔄 Upcoming` |
| **05** | Inodes, Links (`ln`), Storage & Archival (`tar`, `gzip`) | — | — | `🔄 Upcoming` |
| **06** | Network Protocols & Data Ingestion (`curl`, `wget`, `ssh`) | — | — | `🔄 Upcoming` |

---

## 🚀 Week 01 Deep-Dive

<details open>
<summary><b>📂 Click to expand Week 01 Highlights & Solved Problems</b></summary>
<br/>

### 📌 Core Concepts Mastered:
- **Path Resolution:** Absolute (`/level1/level2`) vs Relative (`../level2`, `./script.sh`).
- **File & Directory Mechanics:** `mv`, `cp`, `touch`, `mkdir -p`, `rm -rf`.
- **Pattern Matching (Globbing):** `*` (zero or more chars), `?` (single char), `[a-z]` (ranges).
- **MIME & Header Inspection:** `file *` (determines binary vs ASCII types independent of extension).
- **Security & Octal Math:** User, Group, Others permissions computation.

### 🎯 Fast Problem Solver Index:

| Problem Target | One-Liner Command | Core Concept |
| :--- | :--- | :--- |
| Move all `.txt` files to `level1/` | `mv *.txt level1/` | Globbing & batch transfer |
| Inspect file types across folder | `file *` | Header magic byte check |
| Jump straight to nested directory | `cd /level1/level2` | Absolute path navigation |
| Set permissions: `rwx` (U), `--x` (G), `-w-` (O) | `chmod 712 systemcommands.txt` | $4+2+1=7$, $1=1$, $2=2$ |
| Create file with octal name for `r-x`, `r--`, `-w-` | `touch 542.digits` | Octal representation math |
| Create multiple directories in one call | `mkdir dir1 dir2` | Multi-target creation |
| Relocate file & purge source directory | `mv dir_1/file_1 dir_2/ && rm -rf dir_1` | Safe chaining & removal |

👉 **[Jump to Full Week 1 Solved Sheet with Step-by-Step Explanations](./Week-01/IITM_BSSE2001_Week1_Bash_Practical_Questions_Solutions.md)**

</details>

---

## ⚡ Core Command Matrix

```bash
# 🧭 1. Navigation & Path Resolution
pwd                      # Print absolute path of current working directory
cd /target/dir           # Jump to absolute path
cd ..                    # Move up one level
cd ~                     # Return to user home ($HOME)

# 📁 2. File & Directory Lifecycle
touch file.txt           # Create empty file or update timestamp
mkdir -p a/b/c           # Create recursive directory tree safely
mv src.txt dest/         # Move or rename file/folder
cp -r folder/ backup/    # Recursively copy directory
rm -rf junk/             # Forceful recursive deletion (exercise care!)

# 🔍 3. Inspection & Telemetry
ls -lah                  # List all items with permissions, owners, and sizes
file *                   # Query actual file format (ignores false extensions)
cat file.txt             # Concatenate and print entire file content

# 🔒 4. Permissions & Octal Calculation
# Read(4) | Write(2) | Execute(1)
chmod 755 app.sh         # Owner: rwx (7) | Group: r-x (5) | Others: r-x (5)
chmod 644 config.json    # Owner: rw- (6) | Group: r-- (4) | Others: r-- (4)
chmod 700 id_rsa         # Owner: rwx (7) | Group: --- (0) | Others: --- (0)
```

---

## 💻 Interactive Terminal Sandbox Preview

```
┌──(iitm-scholar㉿bsse2001)-[~/System-Commands]
└─$ git status
On branch main
Your branch is up to date with 'origin/main'.

┌──(iitm-scholar㉿bsse2001)-[~/System-Commands]
└─$ tree -L 2
.
├── README.md
└── Week-01
    ├── IITM_BSSE2001_Week1_Bash_Practical_Questions_Solutions.md
    ├── IITM_BSSE2001_Week1_Interactive_Notes.md
    └── README.md

1 directory, 4 files
```

---

## 🤝 Contributing & Community

We believe in open, peer-to-peer knowledge sharing! Have a cleaner one-liner? Found an alternative trick for an exam question?

1. **Fork** the repository
2. **Create** your branch: `git checkout -b feature/Week02Solutions`
3. **Commit** your enhancements: `git commit -m 'Add Week 2 text processing notes'`
4. **Push** to branch: `git push origin feature/Week02Solutions`
5. **Open** a Pull Request!

---

## 📜 License & Copyright

Distributed under the **MIT License**. See [`LICENSE`](./LICENSE) for full legal text and permissions.

```text
Copyright (c) 2026 Kartik Chilkoti and Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this study repository and associated documentation files to use, study,
copy, modify, merge, and distribute for educational and non-commercial purposes.
```

---

<div align="center">

### 🌟 Made with ❤️ by Students, for Students
*Dedicated to mastering Linux, Bash, and Systems Engineering.*

⭐ **Star this repo to support the open learning community!**

</div>
