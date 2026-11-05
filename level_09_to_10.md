# Bandit Level 9 → Level 10

**Date:** 5 November 2026

## Objective

Find the next level's password in `data.txt`. The file contains binary data and readable text, so we need to extract the readable strings and identify the line containing the required delimiter.

## Credentials

- **Username:** `bandit9`
- **Password:** `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `strings`
- `grep`
- Text extraction from binary files
- Filtering command output using a pipeline

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Inspect the file

Start by examining the file:

```bash
cat data.txt
```

The output contains random-looking characters and some unreadable data. This makes it difficult to identify the password directly.

### Step 3: Extract readable strings

Use `strings` to extract sequences of printable characters:

```bash
strings -a data.txt
```

**Explanation:**

- `strings` extracts readable character sequences from a file.
- `-a` scans the entire file, including sections that might otherwise be skipped.

### Step 4: Filter the output with grep

The challenge indicates that the password is stored in a line preceded by several `=` characters.

Filter the extracted strings:

```bash
strings -a data.txt | grep "==="
```

**Explanation:**

- `|` sends the output of the first command to the next command.
- `grep "==="` displays lines containing the specified sequence.

This makes the relevant line easier to identify.

### Step 5: Retrieve the next password

Read the matching output and use the password to log in to the next level.

## Next Level Password

```text
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```

## Commands Summary

| Command | Purpose |
|---|---|
| `cat data.txt` | Display file contents |
| `strings -a data.txt` | Extract readable strings from the entire file |
| `grep "==="` | Filter lines containing the specified characters |
| `\|` | Pass output from one command to another |

## Key Takeaway

When a file contains binary data mixed with readable text, `strings` can help extract printable content. Combining it with `grep` makes it easier to locate information matching a known pattern.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)

---

*This writeup documents the commands and solution steps used for the Bandit Level 9 → Level 10 challenge.*
