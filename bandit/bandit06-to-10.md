# OverTheWire: Bandit (Levels 06 – 10)

Notes and command breakdowns for Bandit levels 6 through 10.

---

## 📌 Bandit Level 6 → Level 7

* **Goal:** The password is stored somewhere on the server and has all of the following properties:
  1. Owned by user `bandit7`
  2. Owned by group `bandit6`
  3. Exactly 33 bytes in size
* **Host:** `bandit.labs.overthewire.org`
* **Port:** `2220`
* **User:** `bandit6`
* **Status:** In Progress ⏳

### Commands Used:
```bash
# Connect via SSH:
ssh bandit6@bandit.labs.overthewire.org -p 2220

# Search the entire filesystem from root (/), redirecting permission errors to /dev/null:
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

### What I Learned:
* *(Notes to be added after solving!)*

---

## 📌 Bandit Level 7 → Level 8

* **Goal:** The password is stored in `data.txt` next to the word `millionth`.
* **Commands Used:**
  ```bash
  # TODO: Fill in after solving!
  ```
* **What I Learned:**
  * *(Notes to be added)*
