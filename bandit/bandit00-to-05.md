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

## 📌 Bandit Level 2 → Level 3

* **Goal:** The password is stored in a file named `spaces in this filename` located in the home directory.
* **Commands Used:**
  ```bash
  # TODO: Fill in after solving!
  ```
* **What I Learned:**
  * *(Notes to be added)*
