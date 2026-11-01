# Bandit Level 4 → Level 5

**Platform:** OverTheWire Bandit  
**Level:** 4 → 5  
**Date:** 1 November 2026

---

## Objective

The objective of this level is to find the password for the next level.

The password is stored in one of the files inside the `inhere` directory.

The directory contains multiple files, but only one contains human-readable text. The challenge introduces the Linux `file` command, which identifies the type of a file based on its contents.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit4` |
| Password | `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server:

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

Enter the password for `bandit4` when prompted.

## Steps to Solve

**Step 1 — Connect to the server**

Establish an SSH connection to the Bandit environment.

**Step 2 — Navigate to the target directory**

Enter the `inhere` directory:

```bash
cd inhere
```

**Step 3 — Identify file types**

Run the following command:

```bash
file ./*
```

This checks the file types of the files in the current directory.

The output identifies one file as human-readable ASCII text.

**Step 4 — Identify the readable file**

According to the challenge investigation, the readable file is:

```text
-file07
```

**Step 5 — Read the file**

Use `cat` to display its contents:

```bash
cat ./-file07
```

The `./` prefix explicitly identifies the filename, which begins with a hyphen.

**Step 6 — Retrieve the next-level password**

The file contents provide the password required to log in as `bandit5`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `cd` | Change the current directory |
| `file` | Identify file types |
| `cat` | Display file contents |
| `./*` | Expand to matching entries in the current directory |

## Key Takeaways

- Learned how to identify file types using the `file` command.
- Understood the difference between human-readable text and binary data.
- Practiced checking multiple files using a wildcard.
- Learned how to read a file whose name begins with a hyphen.
- Improved Linux command-line investigation skills.

## Next Level Password

```text
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

---

**Previous Level:** [Bandit Level 3 → Level 4](./level_3_to_4.md)

**Next Level:** [Bandit Level 5 → Level 6](./level_5_to_6.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
