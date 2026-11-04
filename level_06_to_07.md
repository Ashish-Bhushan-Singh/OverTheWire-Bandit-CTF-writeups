# Bandit Level 6 → Level 7

**Platform:** OverTheWire Bandit  
**Level:** 6 → 7  
**Date:** 4 November 2026

---

## Objective

The objective of this level is to locate the file containing the password for the next level.

The password is stored somewhere on the server, outside a specific directory.

The target file must meet the following conditions:

- It must be a regular file.
- Its owner must be `bandit7`.
- Its group must be `bandit6`.
- Its size must be exactly 33 bytes.

This challenge introduces searching across the entire Linux filesystem and filtering files using ownership, group membership, and file size.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit6` |
| Password | `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server:

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

Enter the password for `bandit6` when prompted.

## Steps to Solve

**Step 1 — Connect to the server**

Establish an SSH connection to the Bandit environment.

**Step 2 — Search the entire filesystem**

Run the following command:

```bash
find / -type f -user bandit7 -group bandit6 -size 33c
```

This searches the filesystem for files matching the challenge requirements.

**Step 3 — Understand the permission errors**

During the search, many directories may produce messages similar to:

```text
Permission denied
```

This happens because the current user does not have permission to access every directory or file.

**Step 4 — Suppress error messages**

Redirect standard error to `/dev/null`:

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

This keeps the search output cleaner by hiding permission-denied messages.

**Step 5 — Understand the command**

| Option | Explanation |
|---|---|
| `find /` | Search starting from the root directory |
| `-type f` | Match regular files only |
| `-user bandit7` | Match files owned by `bandit7` |
| `-group bandit6` | Match files belonging to group `bandit6` |
| `-size 33c` | Match files exactly 33 bytes in size |
| `2>` | Redirect standard error |
| `/dev/null` | Discard redirected output |

**Step 6 — Identify the matching file**

The search identifies the following file:

```text
/var/lib/dpkg/info/bandit7.password
```

**Step 7 — Read the file**

Use `cat` to display its contents:

```bash
cat /var/lib/dpkg/info/bandit7.password
```

**Step 8 — Retrieve the next-level password**

The file contains the password required to log in as `bandit7`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `find` | Search for files and directories |
| `cat` | Display file contents |
| `2>` | Redirect standard error |
| `2>/dev/null` | Discard error messages |

## Key Takeaways

- Learned how to search across the entire Linux filesystem.
- Practiced filtering files by owner and group.
- Understood how to search for files with an exact size.
- Learned why permission-denied messages appear during filesystem searches.
- Understood standard error redirection using file descriptor `2`.
- Learned how `/dev/null` can discard unwanted output.
- Improved Linux filesystem investigation skills.

## Next Level Password

```text
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```

---

**Previous Level:** [Bandit Level 5 → Level 6](./level_5_to_6.md)

**Next Level:** [Bandit Level 7 → Level 8](./level_7_to_8.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
