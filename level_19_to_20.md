# Bandit Level 19 → Level 20

**Date:** 7 November 2026

## Objective

Use the provided SUID executable to execute a command with the privileges of its owner and retrieve the password for `bandit20`.

## Credentials

- **Username:** `bandit19`
- **Password:** `cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- SUID (Set User ID)
- Executable permissions
- `./` for executing a file in the current directory
- Command execution with elevated file-owner privileges

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Execute the provided SUID binary

Run the following command:

```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```

**Explanation:**

- `./bandit20-do` executes the provided binary from the current directory.
- `cat` is the command passed to the binary.
- `/etc/bandit_pass/bandit20` is the file containing the next level's password.

The `bandit20-do` executable has the SUID permission enabled. It runs with the effective user ID of the executable's owner, allowing the command to access the password file as `bandit20`.

### Step 3: Retrieve the next password

The command displays the contents of the password file in the terminal.

Copy the returned password and use it to access the next Bandit level.

## Next Level Password

```text
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```

## Commands Summary

| Command | Purpose |
|---|---|
| `./bandit20-do` | Execute the provided SUID binary |
| `cat` | Display file contents |
| `./bandit20-do cat /etc/bandit_pass/bandit20` | Read the next level's password using the binary |

## Key Takeaway

SUID (Set User ID) is a special Linux permission that allows an executable to run with the effective user ID of its file owner.

This challenge demonstrates why SUID permissions are important in Linux security: an executable with SUID enabled may access resources that the user launching it cannot normally access.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [Linux chmod Manual](https://man7.org/linux/man-pages/man1/chmod.1.html)
- [Linux execve Manual](https://man7.org/linux/man-pages/man2/execve.2.html)

---

*This writeup documents the commands and solution steps used for the Bandit Level 19 → Level 20 challenge.*
