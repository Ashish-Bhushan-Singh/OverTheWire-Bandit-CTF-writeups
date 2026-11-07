# Bandit Level 17 → Level 18

**Date:** 7 November 2026

## Objective

Compare two files, `passwords.old` and `passwords.new`, to identify the line that has changed. The changed line contains the password for the next level.

## Credentials

- **Username:** `bandit17`
- **Password:** `EReVavePLFHtFlFsjn3hyzMlvSuSAcRD`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `diff`
- File comparison
- Identifying differences between text files

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Compare the two files

Run the following command:

```bash
diff passwords.old passwords.new
```

**Explanation:**

- `diff` compares the contents of two files.
- `passwords.old` is the original file.
- `passwords.new` is the updated file.

The command displays the differences between the two files.

### Step 3: Identify the changed line

The output uses symbols to indicate differences:

- `<` indicates a line from the first file (`passwords.old`).
- `>` indicates a line from the second file (`passwords.new`).

In this challenge, the changed line in `passwords.new` contains the next level's password.

### Step 4: Retrieve the next password

Identify the password shown in the output and use it to access the next Bandit level.

## Next Level Password

```text
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```

## Commands Summary

| Command | Purpose |
|---|---|
| `diff` | Compare two files and display their differences |
| `diff passwords.old passwords.new` | Identify changes between the two password files |

## Key Takeaway

The `diff` command is useful when comparing two versions of a file. It helps identify added, removed, or modified lines without manually checking the entire contents.

In this challenge, comparing the two password files makes it possible to identify the single changed line containing the next password.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [GNU Diffutils Manual](https://www.gnu.org/software/diffutils/manual/)

---

*This writeup documents the commands and solution steps used for the Bandit Level 17 → Level 18 challenge.*
