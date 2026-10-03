<div align="center">

# 🐧 Week 01: Linux & Bash Foundations
### *BSSE2001: System Commands — Interactive Learning Vault*

[![Week Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge&logo=checkmarx&logoColor=white)](#)
[![Bash](https://img.shields.io/badge/Bash-Practice_Solved-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)](#)
[![Purpose](https://img.shields.io/badge/Purpose-Self_Study_%26_Peer_Learning-blue?style=for-the-badge)](#)

[⬅️ Back to Main Repository](../README.md) • [📘 Interactive Notes](./Week1_Interactive_Notes.md) • [🎯 Solved Question Bank](./Week1_Bash_Practical_Questions_Solutions.md)

---

</div>

> [!NOTE]
> This module is part of an open, student-created learning repository designed for hands-on practice, concept clarity, and practical mastery of System Commands.

## 📚 Contents in this Folder

| File | Type | Description |
| :--- | :---: | :--- |
| **[`Week1_Interactive_Notes.md`](./Week1_Interactive_Notes.md)** | 📘 Comprehensive Notes | In-depth theory, file tree mental models, command mechanics, options, and practical terminal workflows. |
| **[`Week1_Bash_Practical_Questions_Solutions.md`](./Week1_Bash_Practical_Questions_Solutions.md)** | 🎯 Question Bank | Exact practice problems with one-liner commands, mathematical breakdowns, and common traps. |

---

## 🔑 Key Concepts & Cheatsheet

### 1. File Permissions Octal Breakdown
| Character Notation | Binary | Decimal Value | Meaning |
| :---: | :---: | :---: | :--- |
| `---` | `000` | **0** | No permissions |
| `--x` | `001` | **1** | Execute only |
| `-w-` | `010` | **2** | Write only |
| `-wx` | `011` | **3** | Write + Execute |
| `r--` | `100` | **4** | Read only |
| `r-x` | `101` | **5** | Read + Execute |
| `rw-` | `110` | **6** | Read + Write |
| `rwx` | `111` | **7** | Read + Write + Execute (Full control) |

*Formula:*  
$$\text{Permission} = \mathbf{Owner}(r+w+x) \quad \mathbf{Group}(r+w+x) \quad \mathbf{Others}(r+w+x)$$

### 2. Wildcards vs RegEx
* `*` : Matches 0 or more arbitrary characters. E.g. `*.txt`
* `?` : Matches exactly 1 character. E.g. `file?.log`
* `[abc]` : Matches any character inside the set.

---

[⬅️ Return to Root](../README.md)
