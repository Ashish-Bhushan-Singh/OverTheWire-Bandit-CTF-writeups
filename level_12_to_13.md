# Bandit Level 12 → Level 13

**Date:** 6 November 2026

## Objective

Recover the next level's password from a file containing a hexdump of repeatedly compressed data.

The task involves reversing the hexdump and identifying each file format before extracting or decompressing its contents.

## Credentials

- **Username:** `bandit12`
- **Password:** `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `xxd`
- `file`
- `tar`
- `gzip`
- `bzip2`
- `cat`
- Hexadecimal conversion
- File identification and decompression

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Inspect the file

Start by displaying the contents:

```bash
cat data.txt
```

The output is a hexdump rather than ordinary readable text.

### Step 3: Reverse the hexdump

Use `xxd` with the `-r` option to convert the hexdump back into its original binary data.

For example:

```bash
xxd -r data.txt > /tmp/data
```

**Explanation:**

- `xxd` creates a hexadecimal representation of binary data.
- `-r` reverses the operation and converts a hexdump back into binary data.
- `>` redirects the output into a file.
- `/tmp/data` is a working copy used for further analysis.

### Step 4: Identify and decompress the file

Use the `file` command to identify the actual format:

```bash
file /tmp/data
```

Depending on the identified format, use the appropriate command.

**For TAR archives:**

```bash
tar xf filename
```

**For GZIP-compressed files:**

```bash
gzip -d filename
```

**For BZIP2-compressed files:**

```bash
bzip2 -d filename
```

After each extraction or decompression, identify the resulting file again:

```bash
file filename
```

Repeat this process until the remaining content is readable text containing the next password.

**Important:** Work with temporary copies and use the filename produced by each extraction step. The file format determines which command should be used next.

### Step 5: Retrieve the next password

Read the final text file and use the recovered password to access the next Bandit level.

## Next Level Password

```text
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

## Commands Summary

| Command | Purpose |
|---|---|
| `xxd` | Create a hexadecimal representation of binary data |
| `xxd -r` | Reverse a hexdump into binary data |
| `file` | Identify a file's format |
| `tar xf` | Extract a TAR archive |
| `gzip -d` | Decompress a GZIP file |
| `bzip2 -d` | Decompress a BZIP2 file |
| `cat` | Display file contents |
| `>` | Redirect command output into a file |

## Key Takeaway

A file's extension does not always reveal its actual format. The `file` command helps identify the content so you can choose the correct extraction or decompression tool.

This challenge demonstrates a practical file-analysis workflow: reverse the hexdump, identify the format, decompress or extract the file, and repeat until the original readable content is recovered.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [xxd Manual](https://linux.die.net/man/1/xxd)
- [GNU tar Manual](https://www.gnu.org/software/tar/manual/)

---

*This writeup documents the commands and solution approach used for the Bandit Level 12 → Level 13 challenge.*
