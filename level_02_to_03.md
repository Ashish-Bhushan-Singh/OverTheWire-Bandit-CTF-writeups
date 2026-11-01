# Bandit Level 2 → Level 3

**Platform:** OverTheWire Bandit  
**Level:** 2 → 3  
**Date:** 1 November 2026

---

## Objective

The objective of this level is to retrieve the password for the next level.

The password is stored in a file whose name contains multiple spaces:

```text
--spaces in this filename--
```

The challenge introduces handling filenames containing spaces and locating files in the Linux filesystem.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit2` |
| Password | `263JGJPfgU6LtdEvgfWU1XP5yac29mFx` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server:

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

Enter the password for `bandit2` when prompted.

## Steps to Solve

**Step 1 — Connect to the server**

Use SSH to access the Bandit environment.

**Step 2 — List files in the current directory**

Run:

```bash
ls -la
```

This displays all directory entries, including hidden files and their permissions.

**Step 3 — Identify the filename**

Locate the file named:

```text
--spaces in this filename--
```

The filename contains spaces, so it must be handled carefully when passing it to a command.

**Step 4 — Read the file**

Use the following command to read the file:

```bash
cat "./--spaces in this filename--"
```

Alternatively, escape the spaces:

```bash
cat ./--spaces\ in\ this\ filename--
```

**Step 5 — Retrieve the next-level password**

The file contents reveal the password required to access `bandit3`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `ls -la` | List all files, including hidden entries, with details |
| `cat` | Display file contents |
| `\` | Escape special characters such as spaces |
| `./` | Explicitly reference a file in the current directory |

## Key Takeaways

- Learned how to list hidden files and directory entries.
- Understood why spaces in filenames require special handling.
- Practiced escaping spaces using backslashes.
- Learned to use quotes to handle filenames containing spaces.
- Improved familiarity with Linux file navigation.

## Next Level Password

```text
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

---

**Previous Level:** [Bandit Level 1 → Level 2](./level_1_to_2.md)

**Next Level:** [Bandit Level 3 → Level 4](./level_3_to_4.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
