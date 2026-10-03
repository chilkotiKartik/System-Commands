# BSSE2001: System Commands — Interactive Notes
## Week 1: Command Line Environment & Simple Linux Commands

> **Study mode:** Easy English • Concept-driven • Practical Experiments • Interactive Markdown  
> **Purpose:** Created purely for student peer-to-peer learning and open knowledge sharing.  
> **Course Module:** BSSE2001 — System Commands (Week 1 Scope)  

---

## How to use these notes

This is not meant to be read like a boring PDF.

Use this cycle:

**Understand → Type the command → Predict the output → Run it → Explain it in your own words**

- [ ] Read the concept
- [ ] Type the example in Ubuntu/Linux
- [ ] Try the **Predict** boxes before opening the answer
- [ ] Complete the practice checklist
- [ ] Finish the final quiz without looking at the answers

> **Golden rule:** Do not memorize commands only. Understand **what problem the command solves**.

---

# 0. Week 1 Big Picture

The core curriculum describes Week 1 around:

- GNU/Linux introduction
- Setting up and running a Linux environment
- Command-line environment
- Hardware information
- System information
- Packages
- Input/output redirection

The three lectures you supplied concentrate heavily on the **command-line environment and simple Linux commands**.

### The mental model

```text
You
 ↓
Terminal
 ↓
Shell (e.g. Bash)
 ↓
Linux system / programs
 ↓
Files, directories, hardware, processes, etc.
```

Think of the terminal as the **door** and the shell as the **person understanding what you type**.

---

# 1. Linux: What exactly is it?

## 1.1 Linux is a kernel

A very common beginner mistake is:

> "Linux = an operating system."

More precisely:

**Linux is the kernel.**

The kernel is the core software that communicates with hardware and provides important services to programs.

```text
Applications
     ↓
Shell / Desktop Environment
     ↓
Linux Kernel
     ↓
Hardware
```

### What does the kernel handle?

Examples:

- CPU management
- Memory management
- Devices
- Filesystems
- Processes
- Hardware communication
- Security and access control

---

## 1.2 Then what is Ubuntu?

Ubuntu is a **Linux distribution** (distro).

A distribution combines the Linux kernel with many other components so that you get a usable operating system.

Examples of Linux distributions:

- Ubuntu
- Debian
- Fedora
- Arch Linux
- Linux Mint

### Easy distinction

| Term | Easy meaning |
|---|---|
| Linux kernel | Core of the system |
| Distribution | Complete packaged Linux-based operating system |
| Ubuntu | One Linux distribution |
| Terminal | Program through which you interact with a shell |
| Shell | Program that interprets commands |

---

# 2. GUI vs CLI

## 2.1 GUI

**GUI = Graphical User Interface**

You interact using things such as:

- Mouse
- Windows
- Buttons
- Menus
- Icons

Example:

```text
Open folder
   ↓
Double-click
   ↓
Select file
   ↓
Right-click
   ↓
Rename
```

Easy for beginners, but repetitive operations can become slow.

---

## 2.2 CLI

**CLI = Command Line Interface**

Instead of clicking, you type commands.

Example:

```bash
mv old_name.txt new_name.txt
```

This means:

> Move/rename `old_name.txt` as `new_name.txt`.

### Why CLI matters

The command line is powerful because commands can be:

- precise
- fast
- combined
- automated
- used remotely
- placed inside scripts

Imagine renaming 10,000 files.

GUI:

```text
click → rename → click → rename → ...
```

CLI can automate the operation.

---

## 2.3 GUI vs CLI — remember this

| GUI | CLI |
|---|---|
| Visual | Text-based |
| Mouse + keyboard | Mostly keyboard |
| Beginner-friendly | Takes practice |
| Good for visual work | Excellent for automation |
| Harder to automate complex repetitive actions | Easy to automate |
| Buttons/menus | Commands |

> **Exam idea:** The major advantage of CLI is not simply "it looks faster." Its major power is **precision, composability and automation**.

---

# 3. Terminal vs Shell

This distinction is extremely important.

## Terminal

A **terminal** is the interface/application that lets you interact with a shell.

Examples:

- GNOME Terminal
- Konsole
- Windows Terminal
- xterm

## Shell

A **shell** is a program that interprets your commands.

Examples:

- Bash
- Zsh
- Fish

### Think of it like this

```text
Terminal = classroom
Shell    = teacher who understands your instructions
You      = student giving instructions
```

You type:

```bash
pwd
```

The terminal displays it, but the **shell interprets and executes the command**.

---

# 4. Command Prompt

When you open a shell, you normally see something like:

```text
username@computer:~$
```

Let's break it down.

```text
username @ computer : ~ $
   │          │       │ │
   │          │       │ └── normal-user prompt
   │          │       └────── current location
   │          └────────────── hostname
   └───────────────────────── username
```

### What does `~` mean?

`~` normally represents your **home directory**.

For example:

```text
/home/kartik
```

can be shortened to:

```text
~
```

So:

```bash
cd ~
```

means:

> Go to my home directory.

---

# 5. `$` vs `#`

This is an important exam trap.

### `$`

Usually indicates a normal user shell.

```text
kartik@machine:~$
```

### `#`

Usually indicates the root/superuser shell.

```text
root@machine:~#
```

The root user has very high privileges.

> **Do not casually run destructive commands as root.**

---

# 6. Current Working Directory

The shell always has a concept of a **current working directory**.

Think:

> "Where am I right now?"

Use:

```bash
pwd
```

`pwd` = **print working directory**

Example:

```bash
$ pwd
/home/kartik
```

This tells you the current location.

---

## Try it

```bash
pwd
```

Then:

```bash
cd /tmp
pwd
```

You should now see something like:

```text
/tmp
```

---

# 7. Paths

A **path** tells Linux where something is.

There are two major types.

## 7.1 Absolute path

Starts from the root `/`.

Example:

```text
/home/kartik/Documents/notes.txt
```

It gives the complete location.

---

## 7.2 Relative path

Starts from the current directory.

Suppose:

```text
/home/kartik
```

is your current directory.

Then:

```text
Documents/notes.txt
```

is a relative path.

---

## `.` and `..`

These are extremely important.

### `.`

Means:

> current directory

Example:

```bash
./script.sh
```

### `..`

Means:

> parent directory

Example:

```bash
cd ..
```

means:

> Go one directory upward.

### Visualize

```text
/home
  └── kartik
       ├── Documents
       ├── Downloads
       └── Projects
```

If you are here:

```text
/home/kartik/Documents
```

then:

```bash
cd ..
```

takes you to:

```text
/home/kartik
```

---

# 8. `ls` — List directory contents

The `ls` command lists files and directories.

```bash
ls
```

Example:

```text
Documents
Downloads
Music
Pictures
Projects
```

---

## `ls -l`

The `-l` option gives a long/detailed listing.

```bash
ls -l
```

Typical structure:

```text
-rw-r--r-- 1 kartik kartik 1200 Oct 3 08:00 notes.txt
```

Important fields include:

```text
permissions
   ↓
-rw-r--r--
           owner
              ↓
            kartik
                    group
                       ↓
                     kartik
                            size
                              ↓
                            1200
```

The long listing also contains modification time and filename.

---

## `ls -a`

Shows hidden files too.

```bash
ls -a
```

You may see:

```text
.
..
.bashrc
.profile
Documents
```

Files beginning with `.` are conventionally hidden from normal `ls` output.

---

## `ls -la`

Very common combination:

```bash
ls -la
```

Meaning:

- `-l` → long format
- `-a` → include hidden files

---

## `ls -i`

Shows inode numbers.

```bash
ls -i
```

Example:

```text
123456 notes.txt
123457 data.txt
```

### What is an inode?

An inode is filesystem metadata associated with a file.

It stores information such as:

- file type
- permissions
- owner
- group
- size
- timestamps
- pointers/references to file data

The filename itself is handled through directory entries.

> You will study inodes more deeply later. For now, remember: **inode = important filesystem metadata identity/reference**.

---

# 9. `cd` — Change directory

Syntax:

```bash
cd DIRECTORY
```

Example:

```bash
cd Documents
```

Go to the parent:

```bash
cd ..
```

Go home:

```bash
cd ~
```

Go to root:

```bash
cd /
```

Go back to the previous directory:

```bash
cd -
```

---

## Predict

Suppose:

```text
pwd
/home/kartik/Documents
```

What does this produce?

```bash
cd ..
pwd
```

<details>
<summary>Click to reveal answer</summary>

```text
/home/kartik
```

</details>

---

# 10. `mkdir` — Make directories

Create a directory:

```bash
mkdir projects
```

Create multiple directories:

```bash
mkdir project1 project2 project3
```

### Nested directories

```bash
mkdir -p college/semester5/systemcommands
```

`-p` creates missing parent directories as needed.

---

# 11. `rmdir` — Remove an empty directory

```bash
rmdir old_folder
```

Important:

> `rmdir` is for **empty directories**.

If the directory contains files, `rmdir` normally fails.

---

# 12. `touch` — Create a file / update timestamp

Create an empty file:

```bash
touch notes.txt
```

Multiple files:

```bash
touch a.txt b.txt c.txt
```

Important:

If the file already exists, `touch` does **not** normally erase its contents.

Instead, it updates its timestamps.

### Remember

```text
touch newfile.txt
       ↓
file doesn't exist → create it

touch existing.txt
       ↓
file exists → update timestamps
```

---

# 13. `rm` — Remove files

Delete a file:

```bash
rm notes.txt
```

Delete multiple files:

```bash
rm a.txt b.txt c.txt
```

### Delete a directory recursively

```bash
rm -r folder
```

`-r` means recursive.

It tells `rm` to go through the directory and its contents.

### ⚠️ Danger

```bash
rm -r
```

can be destructive.

Be extremely careful with:

```bash
rm -rf
```

Especially when combined with elevated privileges.

> **Exam distinction:**  
> `rmdir` → empty directory  
> `rm -r` → directory and its contents recursively

---

# 14. `cp` — Copy

Copy a file:

```bash
cp source.txt destination.txt
```

Example:

```bash
cp notes.txt backup.txt
```

Now you have two files.

---

## Copy a directory

A directory usually requires recursive copying:

```bash
cp -r folder1 folder2
```

Why?

Because Linux must copy:

```text
folder
 ├── file1
 ├── file2
 └── subfolder
      └── file3
```

That entire tree must be traversed.

---

# 15. `mv` — Move OR Rename

This command has two common uses.

## Move

```bash
mv notes.txt Documents/
```

## Rename

```bash
mv old.txt new.txt
```

This is a very important point:

> `mv` can rename a file because renaming is essentially changing the file's directory entry/name rather than copying the file's contents.

---

## `cp` vs `mv`

| Command | Purpose |
|---|---|
| `cp` | Copy |
| `mv` | Move / rename |

### Folder difference

```bash
cp -r source target
```

usually needs `-r` for recursively copying a directory.

```bash
mv source target
```

does not need `-r` merely to move/rename the directory.

---

# 16. `cat` — Display/concatenate files

Display a file:

```bash
cat notes.txt
```

It prints the contents.

You can also concatenate:

```bash
cat file1.txt file2.txt
```

The output is the contents of both.

### Very important word

**Concatenate = join together**

---

# 17. `less` — Read large output comfortably

Instead of printing a huge file directly:

```bash
less notes.txt
```

You can move around inside the output.

Common:

```text
Space → next page
b     → previous page
q     → quit
```

`less` is particularly useful for large files and command output.

---

# 18. `head` — First lines

By default:

```bash
head file.txt
```

shows the first **10 lines**.

To request a specific number:

```bash
head -n 5 file.txt
```

or commonly:

```bash
head -5 file.txt
```

Meaning:

> Show the first 5 lines.

---

# 19. `tail` — Last lines

By default:

```bash
tail file.txt
```

shows the last **10 lines**.

Example:

```bash
tail -n 5 file.txt
```

shows the last 5 lines.

### Easy memory trick

```text
HEAD → beginning
TAIL → ending
```

---

# 20. `wc` — Count lines, words and bytes/characters

Basic:

```bash
wc file.txt
```

Typical output contains counts for:

```text
lines  words  bytes  filename
```

Useful options:

```bash
wc -l file.txt
```

→ number of lines

```bash
wc -w file.txt
```

→ number of words

```bash
wc -c file.txt
```

→ number of bytes

> Be careful: `-c` is bytes, not always the same thing as number of Unicode characters.

---

# 21. `file` — Identify file type

Use:

```bash
file notes.txt
```

Possible result:

```text
notes.txt: ASCII text
```

Another example:

```bash
file /bin/bash
```

may report that it is an ELF executable.

### Why is `file` useful?

A filename extension is not a reliable guarantee of actual file type.

`file` examines the file's content/format signatures and metadata to identify it.

---

# 22. `whereis`

`whereis` can locate:

- binary
- source
- manual pages

Example:

```bash
whereis ls
```

Possible output:

```text
ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
```

---

# 23. `locate`

`locate` searches a pre-built file database.

Example:

```bash
locate notes.txt
```

Important:

> `locate` is database-based, so a very recently created file may not appear until the database is updated.

On systems using `updatedb`, the database can be refreshed.

---

# 24. `type`

`type` tells you how the shell interprets a command.

Example:

```bash
type cd
```

You may get:

```text
cd is a shell builtin
```

For another command:

```bash
type ls
```

may identify an executable or an alias/function depending on your shell configuration.

### Why this matters

Not everything you type is necessarily a standalone executable.

A command can be:

- shell builtin
- alias
- function
- executable

---

# 25. `whoami`

Very simple:

```bash
whoami
```

It tells you the current effective username.

Example:

```text
kartik
```

### Memory trick

> **WHO AM I? → `whoami`**

---

# 26. `groups`

```bash
groups
```

Shows the groups to which the current user belongs.

Example:

```text
kartik sudo plugdev
```

Groups matter because Linux permissions can depend on group membership.

---

# 27. `who`

```bash
who
```

Shows users currently logged into the system and related session information.

Do not confuse:

```text
whoami → who am I?
who    → who is logged in?
```

---

# 28. `passwd`

```bash
passwd
```

Used to change the current user's password.

The root user can have additional administrative ability to change other users' passwords.

---

# 29. Getting Help

Linux has excellent built-in documentation.

Three important approaches are:

```bash
man COMMAND
```

```bash
COMMAND --help
```

```bash
info COMMAND
```

---

## 29.1 `man`

Example:

```bash
man ls
```

`man` = manual pages.

You can use it to understand:

- command purpose
- syntax
- options
- behavior
- examples in some manuals

Exit:

```text
q
```

---

## 29.2 `--help`

Example:

```bash
ls --help
```

Usually gives a quick command reference.

Good when you want a fast reminder.

---

## 29.3 `info`

Example:

```bash
info ls
```

GNU info pages can provide more structured/hypertext-like documentation for some commands.

Common navigation keys include:

```text
q → quit
n → next node
p → previous node
u → up
Enter → follow link
```

---

## 29.4 `help`

`help` is especially useful for **shell builtins**.

Example:

```bash
help cd
```

or:

```bash
help for
```

### Important distinction

```text
man       → manual pages
info      → GNU info documentation
--help    → quick help
help      → shell builtin help
```

---

# 30. Disk Space vs Memory

This is a major conceptual trap.

## `df`

`df` = disk filesystem space.

```bash
df
```

Human-readable:

```bash
df -h
```

It tells you about filesystem storage:

```text
Filesystem
Size
Used
Available
Use%
Mounted on
```

Think:

> **How much storage space is available?**

---

## `du`

`du` = disk usage.

```bash
du
```

It tells you how much space files/directories are using.

Very useful:

```bash
du -sh folder
```

Meaning:

- `-s` → summary
- `-h` → human-readable

---

## `free`

`free` = RAM/memory usage.

```bash
free
```

Human-readable:

```bash
free -h
```

It reports memory and swap information.

---

## The golden distinction

```text
df → filesystem free space
du → directory/file disk usage
free → RAM + swap
```

### Memory trick

```text
DF = Disk Free
DU = Disk Used
FREE = Memory information
```

---

# 31. Human-readable output

Many commands have:

```bash
-h
```

This usually means:

> human-readable

For example:

```bash
df -h
free -h
du -sh .
```

Instead of difficult raw numbers, you may see:

```text
Gi
Mi
Ki
```

---

# 32. MB vs MiB

Do not blindly treat these as identical.

### Decimal/SI

```text
1 MB = 1000 KB
1 GB = 1000 MB
1 TB = 1000 GB
```

### Binary

```text
1 MiB = 1024 KiB
1 GiB = 1024 MiB
1 TiB = 1024 GiB
```

So:

```text
MB ≠ MiB
GB ≠ GiB
```

This difference is useful when interpreting system reports.

---

# 33. A Complete Navigation Example

Suppose your home directory contains:

```text
/home/kartik
├── Documents
├── Downloads
└── Projects
```

You want:

```text
Projects
└── SystemCommands
    └── week1.txt
```

### Step 1 — Go home

```bash
cd ~
```

### Step 2 — Create Projects

```bash
mkdir Projects
```

### Step 3 — Enter Projects

```bash
cd Projects
```

### Step 4 — Create SystemCommands

```bash
mkdir SystemCommands
```

### Step 5 — Enter it

```bash
cd SystemCommands
```

### Step 6 — Create file

```bash
touch week1.txt
```

### Step 7 — Confirm

```bash
ls -l
```

### Step 8 — Confirm location

```bash
pwd
```

---

# 34. One command can take arguments

A command normally has the general idea:

```text
command [options] [arguments]
```

Example:

```bash
ls -l Documents
```

Breakdown:

```text
ls          → command
-l          → option
Documents   → argument
```

Another:

```bash
head -n 5 notes.txt
```

```text
head       → command
-n 5       → option + option value
notes.txt  → argument
```

---

# 35. Options / Flags

Options modify command behavior.

Examples:

```bash
ls -l
ls -a
ls -la
df -h
free -h
du -sh .
cp -r folder backup
```

A very important habit:

> Never assume what an option means. Use the manual.

Example:

```bash
man ls
```

---

# 36. Predict the Command

## Question 1

Current directory:

```text
/home/kartik/Documents
```

Command:

```bash
cd ..
pwd
```

<details>
<summary>Reveal answer</summary>

```text
/home/kartik
```

</details>

---

## Question 2

You have:

```text
file1.txt
```

Command:

```bash
cp file1.txt file2.txt
```

What happens?

<details>
<summary>Reveal answer</summary>

`file2.txt` becomes a copy of `file1.txt`.

The original `file1.txt` remains.

</details>

---

## Question 3

You have:

```text
folder/
└── a.txt
```

What happens with:

```bash
rmdir folder
```

<details>
<summary>Reveal answer</summary>

It fails because `folder` is not empty.

For a recursive removal:

```bash
rm -r folder
```

</details>

---

## Question 4

What does this do?

```bash
touch existing.txt
```

<details>
<summary>Reveal answer</summary>

If the file already exists, `touch` normally updates its timestamps without replacing its contents.

</details>

---

# 37. Command Comparison Table

| Command | Main job | Example |
|---|---|---|
| `pwd` | Show current directory | `pwd` |
| `ls` | List directory | `ls` |
| `cd` | Change directory | `cd Documents` |
| `mkdir` | Create directory | `mkdir test` |
| `rmdir` | Remove empty directory | `rmdir test` |
| `touch` | Create file/update timestamp | `touch a.txt` |
| `rm` | Remove file | `rm a.txt` |
| `rm -r` | Remove directory recursively | `rm -r test` |
| `cp` | Copy | `cp a b` |
| `cp -r` | Copy directory recursively | `cp -r A B` |
| `mv` | Move/rename | `mv a b` |
| `cat` | Display/concatenate | `cat a.txt` |
| `less` | Browse output/file | `less a.txt` |
| `head` | First lines | `head -n 5 a.txt` |
| `tail` | Last lines | `tail -n 5 a.txt` |
| `wc` | Count | `wc -l a.txt` |
| `file` | Identify file type | `file a.txt` |
| `whereis` | Locate command/binary/man | `whereis ls` |
| `locate` | Search indexed file database | `locate a.txt` |
| `type` | Explain command type | `type cd` |
| `whoami` | Current user | `whoami` |
| `groups` | User groups | `groups` |
| `who` | Logged-in users | `who` |
| `passwd` | Change password | `passwd` |
| `man` | Manual | `man ls` |
| `info` | GNU info documentation | `info ls` |
| `help` | Shell builtin help | `help cd` |
| `df` | Filesystem free space | `df -h` |
| `du` | Disk usage | `du -sh .` |
| `free` | Memory/swap | `free -h` |

---

# 38. The Most Important Differences

## `cp` vs `mv`

```text
cp → duplicate
mv → move / rename
```

## `rm` vs `rmdir`

```text
rmdir → empty directory only
rm     → files; with -r, directories recursively
```

## `df` vs `du`

```text
df → filesystem storage availability
du → storage used by files/directories
```

## `who` vs `whoami`

```text
who    → logged-in users
whoami → current effective user
```

## `man` vs `help`

```text
man  → manual pages
help → shell builtin help
```

## `head` vs `tail`

```text
head → beginning
tail → end
```

## `whereis` vs `locate`

```text
whereis → locations associated with a command
locate  → searches indexed filenames
```

---

# 39. Mini Practical Lab

Open Ubuntu and do these **in order**.

```bash
cd ~
mkdir sc_week1
cd sc_week1
touch a.txt b.txt c.txt
mkdir folder1 folder2
ls -la
pwd
cp a.txt folder1/
mv b.txt folder2/
mv c.txt renamed.txt
ls -R
du -sh .
df -h .
free -h
file renamed.txt
whoami
groups
```

Then try:

```bash
cd ..
```

and:

```bash
rm -r sc_week1
```

### Before running the final command

Ask yourself:

> "What exactly will be deleted?"

If you cannot answer, **do not run it yet**.

---

# 40. Exam-Oriented Questions

## MCQ 1

Which command prints the current working directory?

A. `ls`  
B. `pwd`  
C. `cd`  
D. `dir`

<details>
<summary>Answer</summary>

**B — `pwd`**

</details>

---

## MCQ 2

Which command shows RAM and swap information?

A. `df`  
B. `du`  
C. `free`  
D. `mem`

<details>
<summary>Answer</summary>

**C — `free`**

</details>

---

## MCQ 3

Which command is used to copy a directory recursively?

A. `mv -r`  
B. `cp -r`  
C. `rm -r`  
D. `rmdir -r`

<details>
<summary>Answer</summary>

**B — `cp -r`**

</details>

---

## MCQ 4

What does `~` normally represent?

A. Root directory  
B. Current directory  
C. User's home directory  
D. Parent directory

<details>
<summary>Answer</summary>

**C — User's home directory**

</details>

---

## MCQ 5

Which command can rename a file?

A. `cp`  
B. `mv`  
C. `touch`  
D. `rename-dir`

<details>
<summary>Answer</summary>

**B — `mv`**

</details>

---

## MCQ 6

What does `cd ..` do?

A. Go to root  
B. Go home  
C. Go to parent directory  
D. Delete the current directory

<details>
<summary>Answer</summary>

**C — Go to parent directory**

</details>

---

## MCQ 7

Which command displays the first 5 lines?

A. `tail -5 file`  
B. `head -5 file`  
C. `top -5 file`  
D. `cat -5 file`

<details>
<summary>Answer</summary>

**B — `head -5 file`**

</details>

---

## MCQ 8

Which command displays filesystem disk-space information?

A. `free`  
B. `du`  
C. `df`  
D. `disk`

<details>
<summary>Answer</summary>

**C — `df`**

</details>

---

# 41. Short-Answer Practice

Try answering without looking above.

### Q1. What is the difference between Linux and Ubuntu?

<details>
<summary>Reveal</summary>

Linux is the kernel. Ubuntu is a Linux distribution containing the kernel plus many other components and software needed to provide a usable operating system.

</details>

### Q2. What is a shell?

<details>
<summary>Reveal</summary>

A shell is a program that interprets commands and provides a command-line interface to the operating system.

</details>

### Q3. What is the difference between absolute and relative paths?

<details>
<summary>Reveal</summary>

An absolute path starts from the root `/` and gives the complete location. A relative path is interpreted from the current working directory.

</details>

### Q4. Why is `cp -r` needed for directories?

<details>
<summary>Reveal</summary>

Because copying a directory means recursively copying its contents and subdirectories.

</details>

### Q5. What does `touch` do when a file already exists?

<details>
<summary>Reveal</summary>

It normally updates the file's timestamps without changing its contents.

</details>

---

# 42. Command Prediction Challenge

Do these mentally.

## Challenge A

```bash
mkdir A
cd A
touch one.txt
mkdir B
cp one.txt B/
```

Final structure?

<details>
<summary>Answer</summary>

```text
A/
├── one.txt
└── B/
    └── one.txt
```

</details>

---

## Challenge B

```bash
mkdir test
cd test
touch a.txt
cd ..
rm -r test
```

Final result?

<details>
<summary>Answer</summary>

The `test` directory and its `a.txt` file are removed recursively.

</details>

---

## Challenge C

```bash
pwd
cd /
pwd
cd ~
pwd
```

What are the three locations?

<details>
<summary>Answer</summary>

First: your original current directory.

Second:

```text
/
```

Third: your home directory, e.g.

```text
/home/kartik
```

</details>

---

# 43. Common Mistakes

## Mistake 1 — Thinking `cd` creates a folder

Wrong:

```bash
cd projects
```

does **not** create `projects`.

It only changes directory.

To create:

```bash
mkdir projects
```

Then:

```bash
cd projects
```

---

## Mistake 2 — Thinking `touch` writes text

`touch` does not mean "write text into a file."

Use:

```bash
echo "hello" > file.txt
```

for basic output redirection.

The redirection topic becomes important in the course.

---

## Mistake 3 — Confusing RAM with storage

```text
RAM → free
Disk/filesystem → df
Directory/file disk usage → du
```

---

## Mistake 4 — Thinking `mv` always means "move"

It can also mean **rename**.

```bash
mv old.txt new.txt
```

---

## Mistake 5 — Using `rmdir` on a non-empty folder

```bash
rmdir folder
```

works only when the directory is empty.

---

## Mistake 6 — Forgetting `-r`

For recursive directory copying:

```bash
cp -r folder1 folder2
```

For recursive deletion:

```bash
rm -r folder
```

---

# 44. One-Page Memory Map

```text
                    LINUX CLI
                       │
          ┌────────────┴────────────┐
          │                         │
       NAVIGATION                FILES
          │                         │
    pwd → where am I?         touch → create
    ls  → what is here?       cat   → read
    cd  → move                 cp    → copy
    ~   → home                 mv    → move/rename
    ..  → parent               rm    → remove
                               mkdir → directory
                               rmdir → empty directory
          │
          ├──────── SYSTEM / INFO ────────┐
          │                               │
        df → disk filesystem         free → RAM/swap
        du → disk usage              file → file type
        whoami → current user        groups → groups
        who → logged-in users
          │
          ├──────── DOCUMENTATION ────────┐
          │                               │
        man → manual                  info → GNU info
        help → shell builtin help     --help → quick help
          │
          └──────── SEARCH / COMMAND ─────┐
                                          │
        whereis → command locations
        locate  → indexed file search
        type    → how shell interprets command
```

---

# 45. Must-Memorize Commands

If you have only a few minutes, memorize these first:

```bash
pwd
ls
ls -la
cd
cd ..
cd ~
mkdir
rmdir
touch
rm
rm -r
cp
cp -r
mv
cat
less
head
tail
wc
file
whoami
groups
who
df -h
du -sh
free -h
man
info
help
type
whereis
locate
```

---

# 46. Final 20-Second Revision

### Navigation

```text
pwd = where am I?
ls = what is here?
cd = go somewhere
~ = home
.. = parent
```

### File management

```text
mkdir = make directory
rmdir = remove empty directory
touch = create/update timestamp
cp = copy
mv = move/rename
rm = remove
```

### Reading

```text
cat = show/concatenate
less = browse
head = beginning
tail = end
wc = count
```

### System information

```text
df = filesystem disk space
du = disk usage
free = memory/swap
file = file type
```

### User information

```text
whoami = current user
groups = user's groups
who = logged-in users
```

### Help

```text
man = manual
info = GNU info
help = shell builtin help
--help = quick help
```

---

# 47. Final Self-Test — Don't Peek

Try answering all of these before opening the answers.

1. What is Linux?
2. What is Ubuntu?
3. What is a shell?
4. What is a terminal?
5. Difference between GUI and CLI?
6. What does `$` normally indicate?
7. What does `~` mean?
8. What does `..` mean?
9. Absolute vs relative path?
10. What does `pwd` do?
11. What does `ls -a` do?
12. What does `ls -l` show?
13. What is an inode?
14. Why use `cp -r`?
15. Difference between `cp` and `mv`?
16. Difference between `rm` and `rmdir`?
17. What happens when `touch` is used on an existing file?
18. What does `head` show?
19. What does `tail` show?
20. What does `wc -l` count?
21. What does `file` do?
22. What does `type` tell you?
23. Difference between `who` and `whoami`?
24. Difference between `df` and `du`?
25. What does `free -h` show?
26. Why is `-h` useful?
27. Difference between `man`, `info`, `help`, and `--help`?
28. What does `whereis` do?
29. How is `locate` different from a live filesystem search?
30. Why should recursive `rm` be used carefully?

<details>
<summary>Open answer key</summary>

1. Linux is the kernel used by many Linux-based operating systems.
2. Ubuntu is a Linux distribution.
3. A shell interprets commands.
4. A terminal provides an interface for interacting with a shell.
5. GUI is graphical; CLI is command-based and highly scriptable/automatable.
6. `$` normally represents a normal-user shell prompt.
7. `~` normally means the current user's home directory.
8. `..` means the parent directory.
9. Absolute starts from `/`; relative starts from the current directory.
10. Prints the current working directory.
11. Shows hidden entries as well.
12. Gives long/detailed listing information.
13. An inode stores important filesystem metadata associated with a file.
14. To recursively copy a directory and its contents.
15. `cp` duplicates; `mv` moves or renames.
16. `rmdir` removes empty directories; `rm -r` can recursively remove directories and contents.
17. It normally updates timestamps without replacing the contents.
18. First lines.
19. Last lines.
20. Number of lines.
21. Identifies a file's type/format.
22. How the shell interprets a command.
23. `who` shows logged-in users; `whoami` shows the current effective user.
24. `df` reports filesystem space; `du` reports disk usage by files/directories.
25. Memory and swap information in human-readable form.
26. It makes sizes easier for humans to read.
27. They provide different forms of documentation; `help` is particularly useful for shell builtins.
28. Shows locations associated with a command such as its executable and manual pages.
29. `locate` searches an indexed database, so its results depend on database freshness.
30. It can delete an entire directory tree, so a mistake can cause significant data loss.

</details>

---

# 48. Practical Checklist

Before considering Week 1 command-line basics complete, you should be able to do all of these **without copying from notes**:

- [ ] Open a Linux terminal
- [ ] Identify your current directory
- [ ] Move between directories
- [ ] Use absolute paths
- [ ] Use relative paths
- [ ] Use `.` and `..`
- [ ] Return home with `~`
- [ ] List normal and hidden files
- [ ] Read a long `ls -l` listing
- [ ] Create directories
- [ ] Create files
- [ ] Copy files
- [ ] Copy directories recursively
- [ ] Move files
- [ ] Rename files
- [ ] Remove files
- [ ] Remove empty directories
- [ ] Remove directories recursively **safely**
- [ ] Read files with `cat`
- [ ] Browse files with `less`
- [ ] Use `head` and `tail`
- [ ] Count lines with `wc -l`
- [ ] Identify file types
- [ ] Find command locations
- [ ] Identify your user
- [ ] Check groups
- [ ] Check logged-in users
- [ ] Read `man` pages
- [ ] Use `--help`
- [ ] Understand `df`, `du`, and `free`

---

# 49. What Comes Next?

These commands are the foundation for the rest of System Commands.

```text
Week 1
  ↓
Basic Linux + CLI
  ↓
Week 2
  ↓
Permissions + environment variables + packages
  ↓
Week 3
  ↓
Shell variables + links + processes + remote access
  ↓
Week 4+
  ↓
Pipes + regex + find + editors + Bash
  ↓
AWK + sed + networking + Git
```

The important idea is:

> **Do not study every week as an isolated topic. Linux commands are building blocks. Later weeks combine these blocks into powerful workflows and scripts.**

---

# Scope & verification notes

- This study guide covers **BSSE2001 System Commands** Week‑1 scope.
- Lecture topics covered: **Launching a Linux virtual machine**, **Command line environment**, **Simple commands in Linux Part 1**, and **Simple commands in Linux Part 2**.
- These notes intentionally cover the core lecture topics and add clearly related command explanations/practice needed to understand them.
- Standard reference materials and companion Unix/Linux guides were referenced for command options and syntax accuracy.

---

# ⭐ The one thing to remember

If you remember only one mental model:

```text
WHERE AM I?
    ↓
   pwd

WHAT IS HERE?
    ↓
   ls

WHERE DO I GO?
    ↓
   cd

MAKE SOMETHING
    ↓
 mkdir / touch

COPY IT
    ↓
   cp

MOVE / RENAME IT
    ↓
   mv

REMOVE IT
    ↓
   rm / rmdir

READ IT
    ↓
 cat / less / head / tail

HOW MUCH SPACE?
    ↓
 df / du

HOW MUCH MEMORY?
    ↓
 free

WHO AM I?
    ↓
 whoami

HOW DO I LEARN A COMMAND?
    ↓
 man / info / help / --help
```

**Master this flow and the Linux command line stops looking like random commands. It becomes a language.**
