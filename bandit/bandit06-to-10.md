# OverTheWire: Bandit (Levels 06 – 10)

Notes and command breakdowns for Bandit levels 6 through 10.

---

## 📌 Bandit Level 6 → Level 7 [COMPLETED ✅]

* **Goal:** The password is stored somewhere on the server and has all of the following properties:
  1. Owned by user `bandit7`
  2. Owned by group `bandit6`
  3. Exactly 33 bytes in size
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit6`
* **Status:** Solved ✅

### Commands Used:
```bash
# Connect via SSH:
ssh bandit6@bandit.labs.overthewire.org -p 2220

# Search the entire filesystem from root (/), redirecting permission errors to /dev/null:
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null

# Read the password from the discovered file path:
cat <path-found-by-find>
```

### Engineering Breakdown (Why before How):
* **Problem:** The password file is not in `/home/bandit6`; it is hidden somewhere across the entire server with specific owner (`bandit7`), group (`bandit6`), and size (`33c` = 33 bytes).
* **Mental Model:** Every Linux directory tree starts at root (`/`). When `find /` tries to inspect folders owned by `root` or other users, the kernel rejects access. Because Linux separates normal output (`1`) and error output (`2`), we can silence errors without hiding the actual match.
* **Dead Ends:** Running `find / -type f -user bandit7 -group bandit6 -size 33c` without redirection floods the terminal with hundreds of `Permission denied` lines, burying the single valid file path.

### What I Learned (Standard Streams & `/dev/null`):
* **Linux File Descriptors (`0`, `1`, `2`):** Whenever a command runs, Linux opens three numbered input/output channels (called File Descriptors) for it:
  * **`0` (`stdin` / Standard Input):** Where data enters a program (usually your keyboard, or piped input).
  * **`1` (`stdout` / Standard Output):** Where normal, expected output goes (for example, matching file paths from `find`).
  * **`2` (`stderr` / Standard Error):** Where error and diagnostic messages go (for example, `Permission denied` messages).
  * By default, both `1` and `2` print to your terminal screen, which is why normal results and errors get mixed together.
* **Redirection (`>` and `2>`):**
  * Plain `>` is shorthand for `1>` (send normal output to a file instead of the screen).
  * `2>` targets stream `2` (`stderr`) specifically, leaving stream `1` (`stdout`) on your screen.
* **What `/dev/null` is:**
  * In Linux, hardware devices and virtual devices appear as files inside `/dev/`.
  * `/dev/null` is a special virtual "black hole" device (the null device). Any data written to `/dev/null` is immediately discarded by the kernel and takes up zero disk space.
* **Putting `2>/dev/null` together:**
  * `find` still hits restricted directories and generates errors on stream `2`, but `2>/dev/null` routes all those errors into `/dev/null`, leaving only the real file match (`stdout` stream `1`) visible on screen.
* **Takeaway (Cloud & DevOps relevance):** Splitting `stdout` and `stderr` is essential when managing servers and apps, such as logging normal output and crashes to separate files (`node app.js > app.log 2> error.log`) or silencing noisy cron jobs.

---

## 📌 Bandit Level 7 → Level 8 [COMPLETED ✅]

* **Goal:** The password for the next level is stored in the file `data.txt` next to the word `millionth`.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit7`
* **Status:** Solved ✅

### Commands Used:
```bash
# Connect via SSH:
ssh bandit7@bandit.labs.overthewire.org -p 2220

# Check how many lines are in data.txt before printing it:
wc -l data.txt

# Search for the line containing the word "millionth":
grep "millionth" data.txt
```

### Engineering Breakdown (Why before How):
* **Problem:** `data.txt` contains tens of thousands of random word/password pairs, making manual reading impossible.
* **Mental Model:** Instead of printing the whole file to screen with `cat`, stream the file through a line-by-line pattern filter (`grep`) that discards non-matching lines and prints only the line containing `millionth`.
* **Dead Ends:** Running `cat data.txt` floods the terminal buffer and hides the target line among thousands of lines of noise.

### What I Learned:
* **`wc -l` (Word Count - Lines):** Quick way to check how huge a file is before printing it to your terminal.
* **`grep` (Global Regular Expression Print):** Scans text line by line and outputs only lines matching a pattern.
* **Takeaway (Cloud & DevOps relevance):** Essential for digging through massive server logs in production (for example, `grep "ERROR" app.log` or `grep "502" nginx.log`).

---

## 📌 Bandit Level 8 → Level 9 [COMPLETED ✅]

* **Goal:** The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit8`
* **Status:** Solved ✅

### Commands Used:
```bash
# Connect via SSH:
ssh bandit8@bandit.labs.overthewire.org -p 2220

# Sort lines alphabetically first, then filter for lines that appear only once:
sort data.txt | uniq -u
```

### Engineering Breakdown (Why before How):
* **Problem:** `data.txt` contains thousands of lines where almost every line repeats multiple times, except one unique line.
* **Mental Model:** `uniq` only checks adjacent (back-to-back) lines. By sorting the lines first (`sort`), identical duplicates are grouped side by side so `uniq -u` can drop all repeated groups and leave only the single unique line.
* **Dead Ends:** Running `uniq -u data.txt` without sorting prints almost the entire file because identical lines scattered across different line numbers are not compared against each other.

### What I Learned:
* **`uniq -u`:** Only detects duplicates that sit directly next to each other. Always pair it with `sort` first.
* **The Pipe Operator (`|`):** Connects the `stdout` (channel `1`) of the left command directly into the `stdin` (channel `0`) of the right command without writing a temporary file to disk.
* **Takeaway (Cloud & DevOps relevance):** Sorting and deduplicating output streams (`sort | uniq -c | sort -nr`) is a classic one-liner for counting top error messages or top client IP addresses in server access logs.

---

## 📌 Bandit Level 9 → Level 10 [COMPLETED ✅]

* **Goal:** The password for the next level is stored in the file `data.txt` in one of the few human-readable strings, preceded by several `=` characters.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit9`
* **Status:** Solved ✅

### Commands Used:
```bash
# Connect via SSH:
ssh bandit9@bandit.labs.overthewire.org -p 2220

# Extract printable ASCII sequences from binary data, then filter for lines containing "==":
strings data.txt | grep "=="
```

### Engineering Breakdown (Why before How):
* **Problem:** `data.txt` is mostly non-printable binary data mixed with a few readable ASCII strings.
* **Mental Model:** Instead of dumping binary bytes straight to the terminal with `cat`, use `strings` to extract only sequences of 4 or more printable characters, then pipe (`|`) that clean text output into `grep` to find lines containing `==`.
* **Dead Ends:** Viewing binary files directly with `cat` prints unreadable characters and can corrupt terminal display settings.

### What I Learned:
* **`strings` vs Pipe (`|`):** `strings data.txt` is the tool that extracts readable text from a binary file. The pipe (`|`) does not convert anything to a string by itself; it just acts as a conveyor belt passing `stdout` from the left command (`strings`) into `stdin` of the right command (`grep`).
* **Why `grep "=="` matched `==========` (10 equals signs):** By default, `grep` performs a **substring search**, not an exact whole-word or whole-line match. `grep "=="` asks: "Does this line contain `==` anywhere inside it?" Since `========== password` contains `==` inside it, `grep` matches and prints the entire line. (For exact whole-word or whole-line matching, `grep` uses `-w` or `-x`.)
* **Takeaway (Cloud & DevOps relevance):** `strings` is useful when inspecting compiled binaries, core dumps, or unknown artifacts on a server without corrupting your terminal.

---

## 📌 Bandit Level 10 → Level 11 [COMPLETED ✅]

* **Goal:** The password for the next level is stored in the file `data.txt`, which contains base64 encoded data.
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit10`
* **Status:** Solved ✅

### Commands Used:
```bash
# Connect via SSH:
ssh bandit10@bandit.labs.overthewire.org -p 2220

# Inspect the base64 encoded file:
cat data.txt

# Decode base64 back to readable text:
base64 -d data.txt
```

### Engineering Breakdown (Why before How):
* **Problem:** `data.txt` contains unreadable alphanumeric text ending in `=` / `==` padding instead of plain English words.
* **Mental Model:** Base64 is an encoding scheme (not encryption) that represents raw binary or ASCII bytes using 64 safe printable characters (`A-Z`, `a-z`, `0-9`, `+`, `/`, with `=` as padding). Because it is reversible without any secret key, decoding it immediately reveals the original text.
* **Dead Ends:** Treating Base64 output as a password directly or trying to inspect it with `cat` alone does not decode the underlying payload.

### What I Learned:
* **`base64 -d`:** Decodes Base64-encoded text back into its original form (`-d` = decode; `base64` without `-d` encodes).
* **Encoding vs Encryption:** Encoding (like Base64) transforms data format for safe transport and has zero secrecy; anyone can reverse it. Encryption requires a secret key.
* **Takeaway (Full Stack & Cloud relevance):** JWT payloads in web auth, HTTP Basic Auth headers, and Kubernetes Secrets all use Base64 encoding. Never assume Base64 hides sensitive data.
