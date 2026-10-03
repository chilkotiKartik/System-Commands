<div align="center">

# ⚡ BSSE2001: System Commands
### *The Next-Gen Interactive Learning Vault, Solved Practical Question Bank & Linux Masterclass*

<br/>

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=38BDF8&center=true&vCenter=true&width=720&height=50&lines=Master+Linux+CLI+%26+Bash+Scripting+%F0%9F%90%A7;BSSE2001+System+Commands+Study+Vault+%E2%9A%A1;Interactive+Notes+%2B+Solved+Question+Bank+%F0%9F%93%9D;Purely+For+Learning+%26+Peer+Study+Purposes+%F0%9F%9A%80" alt="Typing SVG" />
</a>

<br/>

[![Educational Purpose](https://img.shields.io/badge/Purpose-Peer_Learning_%26_Self_Study-8B0000?style=for-the-badge&logo=open-access&logoColor=white)](#-educational-purpose--disclaimer)
[![Course Focus](https://img.shields.io/badge/Course-BSSE2001-blue?style=for-the-badge&logo=gnubash&logoColor=white)](https://github.com/chilkotiKartik/System-Commands)
[![Linux](https://img.shields.io/badge/Linux-Terminal_Power-FCC624?style=for-the-badge&logo=linux&logoColor=black)](https://github.com/chilkotiKartik/System-Commands)
[![Bash](https://img.shields.io/badge/Bash-Scripting_Mastery-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)](https://github.com/chilkotiKartik/System-Commands)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](./LICENSE)

<br/>

[📢 Educational Purpose](#-educational-purpose--disclaimer) • [💡 Learning Philosophy](#-innovative-learning-philosophy) • [🗺️ Curriculum Roadmap](#-curriculum--weekly-roadmap) • [🚀 Week 01 Vault](#-week-01-deep-dive) • [⚡ Interactive Matrix](#-core-command-matrix) • [📜 License](#-license--copyright)

---

</div>

> [!IMPORTANT]
> ### 📢 Educational Purpose & Disclaimer
> **This repository is an independent, open-source student study guide created strictly for personal education, peer learning, and self-study purposes.**  
> It is **NOT** an official publication, nor affiliated with or endorsed by any educational institution. All code samples, problem walk-throughs, diagrams, and notes are curated to help students build intuition and command-line fluency.

---

## 💡 Innovative Learning Philosophy

Traditional Linux documentation is often dry and disconnected from practical problem-solving. This repository is built around three core pillars:

```
   ┌─────────────────────────────────────────────────────────────┐
   │                  THE SYSTEM-COMMANDS ENGINE                 │
   └──────────────────────────────┬──────────────────────────────┘
                                  │
         ┌────────────────────────┼────────────────────────┐
         ▼                        ▼                        ▼
  🧠 Visual Mental Models   🎯 Exact Solved Qs       🧪 Terminal Sandbox
  (Inodes, Paths, Math)    (Real Problem Patterns)  (Hands-on experiments)
```

1. **Intuitive Mental Models:** Master octal math, inode hierarchies, and stream redirection through crystal-clear diagrams instead of rote memorization.
2. **Real Problem-Solving Vault:** Solved question banks featuring command breakdowns, exact one-liners, and common trap explanations.
3. **Modular & Interactive:** Each week is structured as a self-contained learning module with direct indexes, cheat sheets, and terminal experiments.

---

## 📁 Repository Blueprint

```
📁 System-Commands/
│
├── 📂 Week-01/                                          # Week 1: Linux & Bash Foundations
│   ├── 📄 README.md                                    # Week 1 Hub & Quick Index
│   ├── 📝 Week1_Interactive_Notes.md                   # In-depth concepts & commands
│   └── 🎯 Week1_Bash_Practical_Questions_Solutions.md  # Solved Qs & Tricks
│
├── 📂 Week-02/                                          # [Upcoming] Text Processing, RegEx, sed, awk
├── 📂 Week-03/                                          # [Upcoming] Shell Scripting & Control Structures
├── 📂 Week-04/                                          # [Upcoming] Process Control & Signals
├── 📂 Week-05/                                          # [Upcoming] Inodes, File Systems & Archives
├── 📄 LICENSE                                          # MIT Open-Source License
└── 📄 README.md                                        # Master repository index
```

---

## 🗺️ Curriculum & Weekly Roadmap

| Week | Focus Topic | Notes | Practice & Solutions | Status |
| :---: | :--- | :---: | :---: | :---: |
| **01** | **Linux Architecture, Navigation, Wildcards & Permissions** | [📘 Notes](./Week-01/Week1_Interactive_Notes.md) | [🎯 Solved Qs](./Week-01/Week1_Bash_Practical_Questions_Solutions.md) | `✅ Completed` |
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

👉 **[Jump to Full Week 1 Solved Sheet with Step-by-Step Explanations](./Week-01/Week1_Bash_Practical_Questions_Solutions.md)**

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
┌──(scholar㉿linux-box)-[~/System-Commands]
└─$ git status
On branch main
Your branch is up to date with 'origin/main'.

┌──(scholar㉿linux-box)-[~/System-Commands]
└─$ tree -L 2
.
├── LICENSE
├── README.md
└── Week-01
    ├── README.md
    ├── Week1_Bash_Practical_Questions_Solutions.md
    └── Week1_Interactive_Notes.md

1 directory, 5 files
```

---

## 🤝 Contributing & Community

We believe in open, peer-to-peer knowledge sharing! Have a cleaner one-liner or alternative practice problem?

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

### 🌟 Made with ❤️ for Open Learning
*Dedicated to mastering Linux, Bash, and Systems Engineering.*

⭐ **Star this repo to support open peer learning!**

</div>
