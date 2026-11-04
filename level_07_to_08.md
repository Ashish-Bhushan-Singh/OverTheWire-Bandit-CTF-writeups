# Bandit Level 7 → Level 8

**Platform:** OverTheWire Bandit  
**Level:** 7 → 8  
**Date:** 4 November 2026

---

## Objective

The objective of this level is to find the password for the next level.

The password is stored in a file named `data.txt`, alongside many other words and values.

The challenge provides a keyword that identifies the correct line:

```text
millionth
```

This level introduces text searching and filtering using the Linux `grep` command.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit7` |
| Password | `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server:

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

Enter the password for `bandit7` when prompted.

## Steps to Solve

**Step 1 — Connect to the server**

Establish an SSH connection to the Bandit environment.

**Step 2 — Read the data file**

Use `cat` to display the contents of `data.txt`:

```bash
cat data.txt
```

The file contains many lines of text and random-looking values, making it difficult to identify the password manually.

**Step 3 — Search for the keyword**

Use `grep` to filter the file and display the line containing the keyword `millionth`:

```bash
cat data.txt | grep --color=always "millionth"
```

**Step 4 — Understand the command**

| Command / Option | Explanation |
|---|---|
| `cat data.txt` | Displays the contents of the file |
| `|` | Sends the output of one command to another |
| `grep` | Searches for matching text |
| `--color=always` | Highlights matching text in the output |
| `"millionth"` | Keyword used to identify the correct line |

**Alternative method**

You can search the file directly without using `cat` and a pipe:

```bash
grep --color=always "millionth" data.txt
```

**Step 5 — Retrieve the next-level password**

The matching line contains the keyword `millionth` followed by the password for `bandit8`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `cat` | Display file contents |
| `grep` | Search for matching text |
| `|` | Pipe output between commands |

## Key Takeaways

- Learned how to search through large text files using `grep`.
- Understood how pipes connect multiple Linux commands.
- Practiced filtering output using a specific keyword.
- Learned how to highlight matching text using `--color=always`.
- Discovered that `grep` can search files directly without requiring `cat`.

## Next Level Password

```text
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

---

**Previous Level:** [Bandit Level 6 → Level 7](./level_6_to_7.md)

**Next Level:** [Bandit Level 8 → Level 9](./level_8_to_9.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
