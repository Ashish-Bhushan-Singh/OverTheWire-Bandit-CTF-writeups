# Bandit Level 8 → Level 9

**Platform:** OverTheWire Bandit  
**Level:** 8 → 9  
**Date:** 4 November 2026

---

## Objective

The objective of this level is to find the password for the next level.

The password is stored in a file named `data.txt`.

The file contains multiple lines of text, but only one line occurs exactly once.

The challenge introduces sorting and duplicate detection using the Linux `sort` and `uniq` commands.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit8` |
| Password | `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server:

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```

Enter the password for `bandit8` when prompted.

## Steps to Solve

**Step 1 — Connect to the server**

Establish an SSH connection to the Bandit environment.

**Step 2 — Inspect the data file**

Use `cat` to display the file contents:

```bash
cat data.txt
```

The file contains many lines, making it difficult to identify the unique entry manually.

**Step 3 — Sort the file and identify the unique line**

Execute:

```bash
sort data.txt | uniq -u
```

This command sorts the lines and identifies the line that occurs exactly once.

**Step 4 — Understand the command**

| Command / Option | Explanation |
|---|---|
| `sort data.txt` | Sorts the lines in the file |
| `|` | Passes the output to another command |
| `uniq` | Identifies repeated or unique adjacent lines |
| `-u` | Displays only lines that occur exactly once |

**Why is `sort` necessary?**

The `uniq` command only compares adjacent lines. Sorting places identical lines next to each other, allowing `uniq -u` to identify the unique entry correctly.

**Step 5 — Retrieve the next-level password**

The output displays the unique line containing the password for `bandit9`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `cat` | Display file contents |
| `sort` | Sort lines of text |
| `uniq` | Identify adjacent duplicate lines |
| `uniq -u` | Display lines occurring exactly once |
| `|` | Connect commands using a pipe |

## Key Takeaways

- Learned how to sort text files using `sort`.
- Understood how `uniq` identifies repeated adjacent lines.
- Learned why sorting is necessary before using `uniq`.
- Practiced identifying unique entries using `uniq -u`.
- Developed useful text-processing skills for analyzing large files.

## Next Level Password

```text
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

---

**Previous Level:** [Bandit Level 7 → Level 8](./level_7_to_8.md)

**Next Level:** [Bandit Level 9 → Level 10](./level_9_to_10.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
