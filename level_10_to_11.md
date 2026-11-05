# Bandit Level 10 → Level 11

**Date:** 5 November 2026

## Objective

Decode a Base64-encoded message in `data.txt` to retrieve the password for the next level.

## Credentials

- **Username:** `bandit10`
- **Password:** `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `base64`
- Base64 encoding and decoding
- Command-line output

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Inspect the file

Display the contents of `data.txt`:

```bash
cat data.txt
```

The content appears encoded rather than being directly readable as the password.

### Step 3: Decode the Base64 content

Use the `base64` command with the `-d` option:

```bash
base64 -d data.txt
```

**Explanation:**

- `base64` is a command-line utility for encoding and decoding data.
- `-d` tells the command to decode the input.
- `data.txt` is the file containing the encoded message.

The command displays the decoded content in the terminal.

### Step 4: Retrieve the next password

Use the decoded output as the password for the next Bandit level.

## Next Level Password

```text
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

## Commands Summary

| Command | Purpose |
|---|---|
| `cat data.txt` | Display the encoded file contents |
| `base64 -d data.txt` | Decode Base64-encoded data |

## Key Takeaway

Base64 is an encoding method, not encryption. When you encounter Base64-encoded content, the `base64 -d` command can decode it into its original representation.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)

---

*This writeup documents the commands and solution steps used for the Bandit Level 10 → Level 11 challenge.*
