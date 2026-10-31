# OverTheWire Bandit — Writeups & Learning Notes

A collection of my personal solutions, notes, and learning experiences from completing the **OverTheWire Bandit Wargame**.

## About Bandit

[OverTheWire Bandit](https://overthewire.org/wargames/bandit/) is a beginner-friendly Linux wargame designed to teach essential Linux command-line skills through practical challenges.

Throughout the challenges, I practiced Linux fundamentals, file navigation, permissions, text processing, networking, SSH, scripting, and other important system administration concepts.

| Information | Details |
|---|---|
| Platform | OverTheWire |
| Wargame | Bandit |
| Difficulty | Beginner to Intermediate |
| Focus | Linux Fundamentals and Command-Line Skills |
| Status | Completed |

## Learning Progress

I have completed the Bandit challenges from Level 0 through Level 33.

Each level has a dedicated Markdown file containing the corresponding solution notes.

| Level | Writeup |
|---|---|
| 0 → 1 | [Level 0 to 1](./level_0_to_1.md) |
| 1 → 2 | [Level 1 to 2](./level_1_to_2.md) |
| 2 → 3 | [Level 2 to 3](./level_2_to_3.md) |
| 3 → 4 | [Level 3 to 4](./level_3_to_4.md) |
| 4 → 5 | [Level 4 to 5](./level_4_to_5.md) |
| 5 → 6 | [Level 5 to 6](./level_5_to_6.md) |
| 6 → 7 | [Level 6 to 7](./level_6_to_7.md) |
| 7 → 8 | [Level 7 to 8](./level_7_to_8.md) |
| 8 → 9 | [Level 8 to 9](./level_8_to_9.md) |
| 9 → 10 | [Level 9 to 10](./level_9_to_10.md) |
| 10 → 11 | [Level 10 to 11](./level_10_to_11.md) |
| 11 → 12 | [Level 11 to 12](./level_11_to_12.md) |
| 12 → 13 | [Level 12 to 13](./level_12_to_13.md) |
| 13 → 14 | [Level 13 to 14](./level_13_to_14.md) |
| 14 → 15 | [Level 14 to 15](./level_14_to_15.md) |
| 15 → 16 | [Level 15 to 16](./level_15_to_16.md) |
| 16 → 17 | [Level 16 to 17](./level_16_to_17.md) |
| 17 → 18 | [Level 17 to 18](./level_17_to_18.md) |
| 18 → 19 | [Level 18 to 19](./level_18_to_19.md) |
| 19 → 20 | [Level 19 to 20](./level_19_to_20.md) |
| 20 → 21 | [Level 20 to 21](./level_20_to_21.md) |
| 21 → 22 | [Level 21 to 22](./level_21_to_22.md) |
| 22 → 23 | [Level 22 to 23](./level_22_to_23.md) |
| 23 → 24 | [Level 23 to 24](./level_23_to_24.md) |
| 24 → 25 | [Level 24 to 25](./level_24_to_25.md) |
| 25 → 26 | [Level 25 to 26](./level_25_to_26.md) |
| 26 → 27 | [Level 26 to 27](./level_26_to_27.md) |
| 27 → 28 | [Level 27 to 28](./level_27_to_28.md) |
| 28 → 29 | [Level 28 to 29](./level_28_to_29.md) |
| 29 → 30 | [Level 29 to 30](./level_29_to_30.md) |
| 30 → 31 | [Level 30 to 31](./level_30_to_31.md) |
| 31 → 32 | [Level 31 to 32](./level_31_to_32.md) |
| 32 → 33 | [Level 32 to 33](./level_32_to_33.md) |
| 33 → 34 | [Level 33 to 34](./level_33_to_34.md) |

## Skills & Tools Learned

The Bandit challenges provided practical experience with the following Linux concepts and commands.

### 1. Linux File System Navigation

- `pwd` — Display the current working directory.
- `ls`, `ls -la` — List files, including hidden files.
- `cd` — Navigate between directories.
- `file` — Identify file types.

### 2. Reading and Inspecting Files

- `cat` — Display file contents.
- `less`, `more` — Read files interactively.
- `head`, `tail` — Display the beginning or end of files.

### 3. Hidden Files and Special Filenames

- Locate hidden files and directories.
- Handle filenames containing spaces.
- Read files with special characters.
- Use quotes and escaping to handle unusual filenames.

### 4. Linux Permissions and Ownership

- `chmod` — Modify file permissions.
- `chown` — Change file ownership.
- `ls -l` — Inspect file permissions.
- Understand Linux permission bits such as `rwxr-xr--`.

### 5. Searching and Filtering

- `grep` — Search for matching text.
- `find` — Locate files based on different criteria.
- `grep -R` — Search recursively through directories.

### 6. Archives and Compression

- `tar` — Extract archive files.
- `gzip` — Decompress gzip files.
- `bzip2` — Decompress bzip2 files.
- `xz` — Decompress xz files.

### 7. Networking and SSH

- `ssh` — Connect to remote systems.
- `nc` — Establish network connections.
- `telnet` — Connect to remote services.
- Understand basic network communication and input/output redirection.

### 8. Redirection and Pipes

- `>` — Redirect output and overwrite a file.
- `>>` — Append output to a file.
- `<` — Read input from a file.
- `|` — Pass output between commands.

Example:

```bash
grep "password" data.txt | sort | uniq
```

### 9. Encoding and Binary Data

- `base64` — Encode and decode Base64 data.
- `xxd` — Inspect hexadecimal data.
- `strings` — Extract printable strings from files.

### 10. Process Management

- `ps` — Display running processes.
- `top`, `htop` — Monitor system activity.
- `kill` — Send signals to processes.

### 11. Shell Scripting and Automation

- Execute shell scripts.
- Work with variables and loops.
- Use command substitution.
- Automate repetitive command-line tasks.

Example:

```bash
for i in {1..10}; do
    echo "$i"
done
```

### 12. Privilege and User Management Fundamentals

- Understand SetUID permissions.
- Switch between users using `su`.
- Understand the purpose of `sudo`.
- Inspect executable permissions and ownership.

## Repository Structure

```text
OverTheWire-Bandit-CTF-writeups/
│
├── README.md
├── level_0_to_1.md
├── level_1_to_2.md
├── level_2_to_3.md
├── ...
└── level_33_to_34.md
```

## Disclaimer

These writeups are intended for educational purposes and personal reference.

All challenges were completed within the OverTheWire Bandit wargame environment. The notes document my learning experience and the techniques I used to solve the challenges.

**Platform:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
