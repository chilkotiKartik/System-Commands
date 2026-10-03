<div align="center">

# ⚡ IIT Madras — BSSE2001: System Commands
### *The Ultimate Interactive Guide, Solved Question Bank & Command-Line Masterclass*

<br/>

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=38BDF8&center=true&vCenter=true&width=650&height=50&lines=Master+Linux+CLI+%26+Bash+Scripting+%F0%9F%90%A7;IIT+Madras+BSSE2001+System+Commands+%F0%9F%8E%93;Interactive+Notes+%2B+Solved+Question+Bank+%F0%9F%93%9D;From+Zero+to+Command-Line+Hero+%E2%9A%A1" alt="Typing SVG" />
</a>

<br/>

[![IIT Madras](https://img.shields.io/badge/IIT_Madras-BS_Degree-8B0000?style=for-the-badge&logo=iit&logoColor=white)](https://study.iitm.ac.in/ds/)
[![Course](https://img.shields.io/badge/Course-BSSE2001-blue?style=for-the-badge&logo=gnubash&logoColor=white)](https://github.com/chilkotiKartik/System-Commands)
[![Linux](https://img.shields.io/badge/Linux-Terminal-FCC624?style=for-the-badge&logo=linux&logoColor=black)](https://github.com/chilkotiKartik/System-Commands)
[![Bash](https://img.shields.io/badge/Bash-Scripting-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)](https://github.com/chilkotiKartik/System-Commands)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

<br/>

[📖 Explore Notes](#-curriculum--weekly-roadmap) • [💡 Question Bank](#-week-01-deep-dive) • [🚀 Quick Cheatsheet](#-core-command-matrix) • [🤝 Contribute](#-contributing)

---

</div>

## 🌟 Overview

Welcome to the **IIT Madras BSSE2001 (System Commands)** comprehensive study repository! This repository is engineered for students and developers seeking crystal-clear conceptual notes, interactive bash experiments, and verified step-by-step practical problem solutions.

```
📁 System-Commands/
│
├── 📂 Week-01/                                          # Week 1: Linux & Bash Foundations
│   ├── 📄 README.md                                    # Week 1 Hub & Quick Index
│   ├── 📝 IITM_BSSE2001_Week1_Interactive_Notes.md     # In-depth concepts & commands
│   └── 🎯 IITM_BSSE2001_Week1_Bash_Practical_Questions_Solutions.md # Solved Qs & Tricks
│
├── 📂 Week-02/                                          # (Coming Soon) Text Processing & Filters
├── 📂 Week-03/                                          # (Coming Soon) Advanced Bash & Scripting
└── 📄 README.md                                        # Master repository index
```

---

## 🗺️ Curriculum & Weekly Roadmap

| Week | Core Focus Area | Notes | Practice & Solutions | Status |
| :---: | :--- | :---: | :---: | :---: |
| **01** | **Linux Architecture, Navigation, Wildcards & Permissions** | [📘 Notes](./Week-01/IITM_BSSE2001_Week1_Interactive_Notes.md) | [🎯 Solved Qs](./Week-01/IITM_BSSE2001_Week1_Bash_Practical_Questions_Solutions.md) | `✅ Completed` |
| **02** | Text Filters, Regex, `grep`, `sed`, `awk` | — | — | `🔄 Upcoming` |
| **03** | Shell Scripting, Control Structures & Functions | — | — | `🔄 Upcoming` |
| **04** | Process Management, Signals & Job Control | — | — | `🔄 Upcoming` |
| **05** | File System Hierarchy, Inodes & Archival (`tar`, `gzip`) | — | — | `🔄 Upcoming` |
| **06** | Network Utilities, SSH, `curl`, `wget` | — | — | `🔄 Upcoming` |

---

## 🚀 Week 01 Deep-Dive

<details open>
<summary><b>📂 Click to expand Week 01 Highlights & Solved Problems</b></summary>
<br/>

### 📌 Core Topics Covered in Week 01:
1. **Linux Navigation & Path Resolution**: `pwd`, `cd`, relative vs. absolute paths (`/level1/level2` vs `../level2`).
2. **File Manipulation & Safe Cleanup**: `mv`, `cp`, `touch`, `mkdir`, `rm -rf`.
3. **Globbing & Wildcards**: `*`, `?`, `[a-z]`, batch operations (e.g. `mv *.txt level1/`).
4. **File Inspection**: `file *`, `ls -la`, identifying file formats without extensions.
5. **Permissions & Octal Math**:
   - `r (4)`, `w (2)`, `x (1)`
   - User / Group / Others mapping (e.g. `chmod 712 file.txt`).

### 🎯 Fast Problem Solver Index:

| Problem Target | Command Solution | Key Concept |
| :--- | :--- | :--- |
| Move all `.txt` files to `level1/` | `mv *.txt level1/` | Wildcard batch move |
| Identify file types across directory | `file *` | Header magic bytes inspection |
| Jump directly into nested directory | `cd /level1/level2` | Absolute path navigation |
| Grant `rwx` (Owner), `--x` (Group), `-w-` (Other) | `chmod 712 systemcommands.txt` | $4+2+1=7$, $1=1$, $2=2$ |
| Calculate octal for `r-x`, `r--`, `-w-` | `touch 542.digits` | Octal string encoding |
| Create multiple folders at once | `mkdir dir1 dir2` | Multi-argument directory creation |
| Move file and remove source folder | `mv dir_1/file_1 dir_2/ && rm -rf dir_1` | Safe chaining & removal |

👉 **[Jump to Full Week 1 Solved Sheet with Step-by-Step Explanations](./Week-01/IITM_BSSE2001_Week1_Bash_Practical_Questions_Solutions.md)**

</details>

---

## ⚡ Core Command Matrix

```bash
# 🧭 Navigation & Directory Hierarchy
pwd                      # Print current absolute working directory
cd /path/to/target       # Change to target directory
cd ..                    # Move up one directory level
cd ~                     # Return to user home directory

# 📁 File & Folder Operations
touch file.txt           # Create an empty file or update timestamp
mkdir -p dir1/dir2       # Create nested directory hierarchy safely
mv source.txt dest/      # Move or rename file
cp -r src_dir/ dest_dir/ # Recursively copy directory
rm -rf old_folder/       # Force recursive deletion (use with caution!)

# 🔍 Inspection & Search
ls -lah                  # List all files with human-readable permissions & sizes
file *                   # Determine true MIME/binary type of all items in current dir
cat filename             # Print file content directly to stdout

# 🔒 Permissions & Security (Octal Calculator)
# r = 4 | w = 2 | x = 1
chmod 755 script.sh      # Owner: rwx (7) | Group: r-x (5) | Others: r-x (5)
chmod 644 document.txt   # Owner: rw- (6) | Group: r-- (4) | Others: r-- (4)
chmod 700 secret.key     # Owner: rwx (7) | Group: --- (0) | Others: --- (0)
```

---

## 💻 Terminal Mockup Preview

```
┌──(iitm-scholar㉿bsse2001)-[~/System-Commands/Week-01]
└─$ ls -la
total 64
drwxr-xr-x 2 scholar scholar  4096 Oct  3 10:30 .
drwxr-xr-x 3 scholar scholar  4096 Oct  3 10:30 ..
-rw-r--r-- 1 scholar scholar 13062 Oct  3 10:30 IITM_BSSE2001_Week1_Bash_Practical_Questions_Solutions.md
-rw-r--r-- 1 scholar scholar 37945 Oct  3 10:30 IITM_BSSE2001_Week1_Interactive_Notes.md
-rw-r--r-- 1 scholar scholar  3420 Oct  3 10:30 README.md

┌──(iitm-scholar㉿bsse2001)-[~/System-Commands/Week-01]
└─$ echo "Ready to ace BSSE2001 exams and assignments! 🚀"
Ready to ace BSSE2001 exams and assignments! 🚀
```

---

## 🛠️ How to Use This Repository

1. **Clone the repository:**
   ```bash
   git clone https://github.com/chilkotiKartik/System-Commands.git
   cd System-Commands
   ```

2. **Navigate to the target week:**
   ```bash
   cd Week-01
   ```

3. **Practice in a live Linux terminal or WSL / Docker container:**
   ```bash
   # Test commands in an isolated sandbox environment
   mkdir -p sandbox && cd sandbox
   touch test{1..5}.txt test{1..3}.log
   mv *.txt ../
   ```

---

## 🤝 Contributing

Contributions, fixes, additional questions, and alternative solutions are warmly welcomed!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/Week02Notes`)
3. Commit your Changes (`git commit -m 'Add Week 2 practice questions'`)
4. Push to the Branch (`git push origin feature/Week02Notes`)
5. Open a Pull Request

---

<div align="center">

### 🎓 IIT Madras BS Degree Program
Crafted with ❤️ for the BSSE2001 community.

⭐ **Star this repo if you find it helpful!**

</div>
