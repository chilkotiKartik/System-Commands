# IIT Madras BSSE2001 — Week 1 Bash Practical Question Bank

## Questions, Exact Solutions, Easy Explanations & Exam Tricks

This sheet contains the Bash/Linux practical questions collected from the Week 1 practice problems, with the exact commands and beginner-friendly explanations.

---

# Quick Index

| Q | Topic | Answer |
|---|---|---|
| 1 | Move all `.txt` files | `mv *.txt level1/` |
| 2 | Print types of all items | `file *` |
| 3 | Make `level2` current directory | `cd /level1/level2` |
| 4 | Set permissions | `chmod 712 systemcommands.txt` |
| 5 | Calculate permission digits + create file | `touch 152.digits` |
| 6 | Create two directories | `mkdir dir1 dir2` |
| 7 | Move file + delete directory | `mv dir_1/file_1 dir_2/` then `rm -rf dir_1` |

---

# Before Starting: 5 Bash Ideas

## 1. `mv`
Moves a file/directory. It can also rename something.

```bash
mv source destination
```

## 2. `*`
A wildcard meaning "match names".

```bash
*.txt
```

means names ending in `.txt`.

```bash
*
```

matches all normal visible entries in the current directory.

## 3. `mkdir`
Creates directories.

```bash
mkdir folder
```

## 4. `touch`
Creates an empty file if it does not exist. For an existing file, it normally updates timestamps without deleting its contents.

```bash
touch file.txt
```

## 5. `chmod`
Changes permissions.

```text
read    = 4
write   = 2
execute = 1
```

---

# Q1 — Move All `.txt` Files

## Question

Write a single Bash command to move **all `.txt` files in the current directory** to the directory `level1`. Do not move any other files.

## Answer

```bash
mv *.txt level1/
```

## Explanation

Break it down:

```text
mv       *.txt       level1/
│          │            │
│          │            └── destination
│          └─────────────── all TXT files
└────────────────────────── move
```

If the current directory contains:

```text
abc.txt
file1.txt
notes.md
photo.pdf
level1/
```

then:

```bash
*.txt
```

matches only:

```text
abc.txt
file1.txt
```

So:

```bash
mv *.txt level1/
```

moves those two files into `level1`.

### Common wrong answers

```bash
mv * level1/
```

Wrong: this can move non-TXT files and directories too.

```bash
cp *.txt level1/
```

Wrong: `cp` copies; it does not move.

### Memory trick

```text
mv     = move
*.txt  = all TXT files
level1 = destination
```

---

# Q2 — Print File Types

## Question

Write a Bash command to print the file types of all files/items in the current working directory. The output should look like:

```text
file.txt: empty
Notes: directory
SysComm: symbolic link to ...
```

## Answer

```bash
file *
```

## Explanation

`file` identifies the type/content format of an item.

For example:

```bash
file abc.txt
```

may produce:

```text
abc.txt: ASCII text
```

The question asks for every item, so use:

```bash
*
```

Therefore:

```bash
file *
```

If the directory contains:

```text
abc.txt
file1.txt
level1
```

you can get:

```text
abc.txt: ASCII text
file1.txt: empty
level1: directory
```

### Common mistake

Do not use:

```bash
ls
```

`ls` lists names; the question asks for their types.

### Remember

```text
file *     → identify everything
file a.txt → identify one item
```

---

# Q3 — Make `level2` the Current Working Directory

## Question

These commands were executed:

```bash
cd /
mkdir level1
cd level1
mkdir level2
cd level2
mkdir level3
cd ..
cd ..
```

Write one Bash command that makes `level2` the current working directory.

## Answer

```bash
cd /level1/level2
```

## Step-by-step

After:

```bash
cd /
```

we are at:

```text
/
```

After creating and entering `level1`:

```text
/level1
```

After creating and entering `level2`:

```text
/level1/level2
```

Then:

```bash
cd ..
```

goes to:

```text
/level1
```

and another:

```bash
cd ..
```

goes to:

```text
/
```

So from `/`, the direct command is:

```bash
cd /level1/level2
```

Verify with:

```bash
pwd
```

Expected path:

```text
/level1/level2
```

### Key concept

```text
/      = root
..     = parent
cd     = change directory
```

---

# Q4 — Set File Permissions

## Question

For:

```text
systemcommands.txt
```

set:

- user: read, write, execute
- group: execute
- others: write

## Answer

```bash
chmod 712 systemcommands.txt
```

## How to calculate `712`

Linux permission values:

```text
read    = 4
write   = 2
execute = 1
```

### User

```text
read + write + execute
4 + 2 + 1 = 7
```

### Group

```text
execute
1
```

### Others

```text
write
2
```

Therefore:

```text
user   group   others
 7       1       2
```

Final:

```text
712
```

So:

```bash
chmod 712 systemcommands.txt
```

## Permission cheat sheet

| Number | Permission |
|---:|---|
| 0 | `---` |
| 1 | `--x` |
| 2 | `-w-` |
| 3 | `-wx` |
| 4 | `r--` |
| 5 | `r-x` |
| 6 | `rw-` |
| 7 | `rwx` |

### Fast method

Always calculate **three groups separately**:

```text
USER | GROUP | OTHERS
```

Never combine all permissions into one calculation.

---

# Q5 — Create `XXX.digits` from Permissions

## Question

For `someFile.txt`, required permissions are:

- user: execute
- group: execute, read
- others: write

The question defines `XXX` as the three-digit permission number and asks you to create:

```text
XXX.digits
```

The file can be empty.

## Step 1 — User

Execute:

```text
1
```

So:

```text
user = 1
```

## Step 2 — Group

Execute + read:

```text
1 + 4 = 5
```

So:

```text
group = 5
```

## Step 3 — Others

Write:

```text
2
```

So:

```text
others = 2
```

Therefore:

```text
152
```

The required filename is:

```text
152.digits
```

## Answer

```bash
touch 152.digits
```

## Why `touch`?

The question says the file can be empty. `touch` is the simplest way to create an empty file.

### Important trap

The answer is **not**:

```bash
chmod 152 someFile.txt
```

The question asks you to create the file:

```text
152.digits
```

So:

```bash
touch 152.digits
```

---

# Q6 — Create Two Directories

## Question

Create:

```text
dir1
dir2
```

in the current working directory using one command.

## Answer

```bash
mkdir dir1 dir2
```

## Explanation

`mkdir` = make directory.

One `mkdir` command can receive multiple directory names:

```bash
mkdir dir1 dir2
```

Result:

```text
current/
├── dir1/
└── dir2/
```

### Common mistake

You could write:

```bash
mkdir dir1
mkdir dir2
```

but that is two commands. The question asks for one line.

---

# Q7 — Move `file_1` and Delete `dir_1`

## Question

Write two commands:

1. Move only `file_1` from `dir_1` to the empty directory `dir_2`.
2. Delete `dir_1`.

`dir_1` and `dir_2` are in the current directory. The current working directory must not change.

## Starting structure

```text
current/
├── dir_1/
│   └── file_1
└── dir_2/
```

## Step 1 — Move the file

```bash
mv dir_1/file_1 dir_2/
```

After this:

```text
current/
├── dir_1/
└── dir_2/
    └── file_1
```

## Step 2 — Delete `dir_1`

A natural answer would be:

```bash
rmdir dir_1
```

but `rmdir` only works if the directory is empty.

In the shown test case, the platform reported:

```text
rmdir: failed to remove 'dir_1': Directory not empty
```

So the robust solution for that test is:

```bash
rm -rf dir_1
```

## Final answer

```bash
mv dir_1/file_1 dir_2/
rm -rf dir_1
```

## What does `rm -rf` mean?

```text
rm = remove
-r = recursive
-f = force
```

It removes the directory and anything remaining inside it.

### ⚠️ Safety note

`rm -rf` is powerful. In a real terminal, always verify the path before running it.

For this controlled practice question, it handles the test case where `dir_1` is still non-empty.

---

# ⭐ Why the First Q7 Attempt Failed

Attempt:

```bash
mv dir_1/file_1 dir_2/
rmdir dir_1
```

The platform returned:

```text
Directory not empty
```

That means moving `file_1` did **not** leave `dir_1` empty.

Therefore:

```bash
rmdir dir_1
```

cannot remove it.

Use:

```bash
rm -rf dir_1
```

instead.

---

# 🔥 Complete Answer Sheet

## Q1

```bash
mv *.txt level1/
```

## Q2

```bash
file *
```

## Q3

```bash
cd /level1/level2
```

## Q4

```bash
chmod 712 systemcommands.txt
```

## Q5

```bash
touch 152.digits
```

## Q6

```bash
mkdir dir1 dir2
```

## Q7

```bash
mv dir_1/file_1 dir_2/
rm -rf dir_1
```

---

# 🧠 Bash Command Map

| If the question says... | Think... |
|---|---|
| move | `mv` |
| copy | `cp` |
| create directory | `mkdir` |
| create empty file | `touch` |
| delete file | `rm` |
| delete empty directory | `rmdir` |
| delete directory recursively | `rm -r` |
| show file type | `file` |
| show current location | `pwd` |
| change location | `cd` |
| all `.txt` files | `*.txt` |
| all visible entries | `*` |
| parent | `..` |
| root | `/` |
| home | `~` |
| change permissions | `chmod` |

---

# 🔢 Permission Number Cheat Sheet

```text
r = 4
w = 2
x = 1
```

```text
0 = ---
1 = --x
2 = -w-
3 = -wx
4 = r--
5 = r-x
6 = rw-
7 = rwx
```

Always write:

```text
USER | GROUP | OTHERS
```

Example:

```text
rwx | r-x | -w-
 7  |  5  |  2

=> 752
```

---

# 🧪 Extra Practice

## Practice 1

Move all `.pdf` files into `documents`.

<details>
<summary>Answer</summary>

```bash
mv *.pdf documents/
```

</details>

## Practice 2

Print the type of every item in the current directory.

<details>
<summary>Answer</summary>

```bash
file *
```

</details>

## Practice 3

Create three directories named `a`, `b`, and `c`.

<details>
<summary>Answer</summary>

```bash
mkdir a b c
```

</details>

## Practice 4

Create an empty file named `test.txt`.

<details>
<summary>Answer</summary>

```bash
touch test.txt
```

</details>

## Practice 5

Set:

```text
user: read + write
group: read
others: execute
```

<details>
<summary>Answer</summary>

```text
user   = 4 + 2 = 6
group  = 4
others = 1

=> 641
```

Command:

```bash
chmod 641 file
```

</details>

## Practice 6

Create this structure in one command:

```text
project/
└── week1/
```

<details>
<summary>Answer</summary>

```bash
mkdir -p project/week1
```

</details>

---

# 🚨 Most Common Exam Traps

### Trap 1: `*` vs `*.txt`

```bash
*
```

matches all normal visible names.

```bash
*.txt
```

matches only names ending in `.txt`.

---

### Trap 2: `cp` vs `mv`

```text
cp = copy
mv = move/rename
```

---

### Trap 3: `rmdir` vs `rm -r`

```text
rmdir = empty directory only
rm -r = directory + contents recursively
```

---

### Trap 4: `touch`

`touch` does not mean "write text".

It creates an empty file if needed and updates timestamps for an existing file.

---

### Trap 5: Permission digits

For:

```text
user: rwx
group: r--
others: -w-
```

calculate separately:

```text
rwx = 7
r-- = 4
-w- = 2
```

Answer:

```text
742
```

---

# 🏆 Final Mental Model

When reading a practical question, first find the **action**:

```text
MOVE?             → mv
COPY?             → cp
CREATE DIRECTORY? → mkdir
CREATE FILE?      → touch
DELETE FILE?      → rm
DELETE EMPTY DIR? → rmdir
DELETE TREE?      → rm -r / rm -rf
PERMISSIONS?      → chmod
FILE TYPE?        → file
WHERE AM I?       → pwd
CHANGE LOCATION?  → cd
```

Then find the **pattern/path**:

```text
all TXT files → *.txt
everything    → *
parent        → ..
home          → ~
root          → /
```

Then construct the command.

Example:

```bash
mv *.txt level1/
```

---

# 🎯 Final 7 Commands to Memorize

```bash
mv *.txt level1/
```

```bash
file *
```

```bash
cd /level1/level2
```

```bash
chmod 712 systemcommands.txt
```

```bash
touch 152.digits
```

```bash
mkdir dir1 dir2
```

```bash
mv dir_1/file_1 dir_2/
rm -rf dir_1
```

> **Best exam strategy:** Do not memorize only the final command. Identify the action, identify the target, check whether a wildcard/option/permission number is required, and then build the command. That makes unfamiliar Bash questions much easier.
