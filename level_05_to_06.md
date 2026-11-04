# Bandit Level 5 → Level 6

**Platform:** OverTheWire Bandit  
**Level:** 5 → 6  
**Date:** 4 November 2026

---

## Objective

The objective of this level is to locate the file containing the password for the next level.

The password is stored somewhere inside the `inhere` directory.

The correct file meets specific conditions:

- It must be a regular file.
- Its size must be exactly 1033 bytes.
- It must not be executable.

This challenge introduces searching for files using multiple conditions with the Linux `find` command.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit5` |
| Password | `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server:

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

Enter the password for `bandit5` when prompted.

## Steps to Solve

**Step 1 — Connect to the server**

Establish an SSH connection to the Bandit environment.

**Step 2 — Navigate to the target directory**

Enter the `inhere` directory:

```bash
cd inhere
```

**Step 3 — Search for the matching file**

Execute the following command:

```bash
find . -type f -size 1033c -not -executable
```

This searches for files matching the challenge requirements.

**Step 4 — Understand the command**

| Option | Explanation |
|---|---|
| `find` | Search for files and directories |
| `.` | Start searching from the current directory |
| `-type f` | Match regular files only |
| `-size 1033c` | Match files exactly 1033 bytes in size |
| `-not -executable` | Exclude files that are executable by the current user |

**Step 5 — Identify the matching file**

The search identifies the following file:

```text
./maybehere07/.file2
```

**Step 6 — Read the file**

Use `cat` to display its contents:

```bash
cat ./maybehere07/.file2
```

**Step 7 — Retrieve the next-level password**

The output contains the password required to log in as `bandit6`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `cd` | Navigate between directories |
| `find` | Search for files and directories |
| `cat` | Display file contents |

## Key Takeaways

- Learned how to search recursively through directories using `find`.
- Understood how to filter regular files using `-type f`.
- Learned how to identify files with an exact size using `-size`.
- Practiced excluding executable files using `-not -executable`.
- Understood how multiple search conditions can be combined.
- Improved Linux file discovery and investigation skills.

## Next Level Password

```text
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

---

**Previous Level:** [Bandit Level 4 → Level 5](./level_4_to_5.md)

**Next Level:** [Bandit Level 6 → Level 7](./level_6_to_7.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
