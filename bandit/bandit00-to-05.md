# OverTheWire: Bandit (Levels 00 – 05)

Notes and takeaways from the first 5 levels of the Bandit wargame.

---

## 📌 Bandit Level 0 → Level 1 [COMPLETED ✅]

* **Goal:** Connect to the remote server via SSH and read the password for Level 1 located in `readme`.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit0`
* **Status:** Solved ✅

### Commands Used:
```bash
# How to connect via SSH:
ssh bandit0@bandit.labs.overthewire.org -p 2220

# List files in the current directory:
ls -la

# Read the contents of the readme file:
cat readme
```

### What I Learned:
* **SSH (Secure Shell):** How to connect securely to a remote Linux machine over the network using port 2220 (`-p 2220`).
* **Host Key Verification:** Understanding that the first time you connect to a server, SSH asks to verify and save its digital fingerprint in `~/.ssh/known_hosts`.
* **Invisible Passwords:** Linux terminal hides cursor/typing when entering passwords for security.
* **`ls` (List):** Shows what files exist in the folder. The `-la` flags show all hidden files (`-a`) and long file details like permissions and size (`-l`).
* **`cat` (Concatenate):** Prints the contents of a file directly to the terminal screen.

---

## 📌 Bandit Level 1 → Level 2 [COMPLETED ✅]

* **Goal:** The password for the next level is stored in a file named `-` located in the home directory.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit1`
* **Status:** Solved ✅

### Commands Used:
```bash
# How to connect via SSH:
ssh bandit1@bandit.labs.overthewire.org -p 2220

# View files in directory:
ls -la

# Read the file named '-':
cat ./-
# Alternative solution:
cat -- -
```

### What I Learned:
* **Standard Input (`stdin`) & the `-` Trap:** In Unix/Linux, a standalone dash `-` represents standard input (keyboard input). Typing `cat -` makes the terminal wait for keyboard input instead of reading a file named `-`.
* **Path Prefix (`./`):** Prepending `./` explicitly instructs the shell to treat the argument as a filesystem path in the current directory, preventing programs from misinterpreting filenames as command-line flags.
* **End-of-Options (`--`):** In POSIX command-line tools, `--` signifies the end of command options/flags. Anything following `--` is treated strictly as a filename or positional argument.

---

## 📌 Bandit Level 2 → Level 3 [COMPLETED ✅]

* **Goal:** The password for the next level is stored in a file named `--spaces in this filename--` located in the home directory.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit2`
* **Status:** Solved ✅

### Commands Used:
```bash
# How to connect via SSH:
ssh bandit2@bandit.labs.overthewire.org -p 2220

# View files in directory:
ls -la

# Reading file with both leading dashes and spaces:
cat -- "--spaces in this filename--"

# Alternative (Path prefix + quotes):
cat ./"--spaces in this filename--"

# Alternative (Tab-completion escape syntax):
cat ./--spaces\ in\ this\ filename--
```

### What I Learned:
* **The Double-Trap (Spaces + Leading Dashes):**
  * Quotes (`"..."`) prevent the shell from breaking the filename into separate arguments on spaces.
  * However, the shell removes quotes before executing the command. `cat` still receives `--spaces...` and treats the leading `--` as a command option/flag, throwing an `unexpected argument` error.
* **Combining Solutions:**
  * Using `--` explicitly tells `cat` to stop expecting flags, allowing `--spaces in this filename--` to be parsed as the target file.
  * Prepending `./` ensures the argument starts with a dot rather than a dash, bypassing option parsers entirely.
* **Tab Autocompletion:** Pressing `Tab` in the terminal automatically handles escape characters (like `\ `) for you.

---

## 📌 Bandit Level 3 → Level 4 [COMPLETED ✅]

* **Goal:** The password is stored in a hidden file inside the `inhere` directory.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit3`
* **Status:** Solved ✅

### Commands Used:
```bash
# Connect via SSH:
ssh bandit3@bandit.labs.overthewire.org -p 2220

# Move into the folder:
cd inhere

# List all files including hidden ones:
ls -la

# Read the hidden file:
cat ...Hiding-From-You
```

### What I Learned:
* **The `.` and `..` Directory Entries:**
  * In Unix filesystems, `.` (single dot) represents the **current directory**.
  * `..` (double dot) represents the **parent directory** (one folder up).
  * This is why `cd ..` moves up a directory, and why running `cat .` results in `cat: .: Is a directory`.
* **Hidden Files Convention:** Any filename beginning with a dot (`.`) is hidden by default. Plain `ls` ignores them; you must pass `-a` (or `-la`) to reveal them.
* **The Filename:** OverTheWire disguised the file as `...Hiding-From-You`. Because it starts with a dot, it was hidden alongside `.` and `..`.

---

## 📌 Bandit Level 4 → Level 5 [COMPLETED ✅]

* **Goal:** The password is stored in the only human-readable file in the `inhere` directory.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit4`
* **Status:** Solved ✅

### Commands Used:
```bash
# Connect via SSH:
ssh bandit4@bandit.labs.overthewire.org -p 2220

# Move into folder:
cd inhere

# Inspect file types of all files in current folder:
file ./*

# Read the single file identified as ASCII text (e.g. -file07):
cat ./-file07
```

### What I Learned:
* **Extensions Don't Matter in Linux:** Unlike Windows, Linux does not care if a file ends in `.txt`, `.exe`, or `.pdf`. A file's true type is determined by its header and binary content.
* **The `file` Command:** Reads the magic numbers/bytes of a file to determine whether it is ASCII text, executable binary, compressed archive, etc.
* **The Asterisk Wildcard (`*`):** `file ./*` tells Linux to run `file` against every file in the current directory.
* **Avoiding Terminal Corruption:** Running `cat` on raw binary data sends non-printable control characters to the terminal, often scrambling the font or causing random beeps. Using `file` first prevents this.

---

## 📌 Bandit Level 5 → Level 6

* **Goal:** The password is stored in a file somewhere under the `inhere` directory and has all of the following properties:
  1. Human-readable (ASCII text)
  2. 1033 bytes in size
  3. Not executable
* **Commands Used:**
  ```bash
  # TODO: Fill in after solving!
  ```
* **What I Learned:**
  * *(Notes to be added)*
