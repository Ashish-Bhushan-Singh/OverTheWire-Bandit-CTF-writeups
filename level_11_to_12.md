# Bandit Level 11 → Level 12

**Date:** 5 November 2026

## Objective

Decode the contents of `data.txt`. The message has been encrypted using ROT13, where each letter is shifted 13 positions through the alphabet.

## Credentials

- **Username:** `bandit11`
- **Password:** `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `cat`
- `tr`
- ROT13
- Character translation

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Inspect the file

Display the contents of `data.txt`:

```bash
cat data.txt
```

The text appears readable, but its letters have been rotated using the ROT13 substitution method.

### Step 3: Decode the ROT13 message

There are two ways to decode the message.

**Method 1: Use a ROT13 decoder**

Open the online [ROT13 Decoder](https://cryptii.com/pipes/rot13-decoder) and enter the contents of `data.txt`.

**Method 2: Use the Linux `tr` command**

Run:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

**Explanation:**

- `cat data.txt` displays the file contents.
- `|` passes the output to the next command.
- `tr` translates characters from one set into another.
- `A-Za-z` represents uppercase and lowercase English letters.
- `N-ZA-Mn-za-m` maps each letter to the letter 13 positions ahead, wrapping around the alphabet.

Because ROT13 shifts letters by 13 positions, applying the same transformation again restores the original text.

### Step 4: Retrieve the next password

Read the decoded output and use it as the password for the next Bandit level.

## Next Level Password

```text
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

## Commands Summary

| Command | Purpose |
|---|---|
| `cat data.txt` | Display the file contents |
| `tr 'A-Za-z' 'N-ZA-Mn-za-m'` | Translate letters using ROT13 |
| `\|` | Pass command output to another command |

## Key Takeaway

ROT13 is a substitution cipher that rotates each letter by 13 positions. It is not secure encryption because the same transformation can decode the message.

The Linux `tr` command provides a simple way to perform character transformations directly in the terminal.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [ROT13 Decoder – Cryptii](https://cryptii.com/pipes/rot13-decoder)

---

*This writeup documents the commands and solution steps used for the Bandit Level 11 → Level 12 challenge.*
