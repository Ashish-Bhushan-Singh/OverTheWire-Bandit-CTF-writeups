# Bandit Level 18 → Level 19

**Date:** 7 November 2026

## Objective

Retrieve the next level's password even though the `bandit18` account automatically terminates interactive SSH sessions.

Instead of opening an interactive shell, execute a command directly through SSH to read the `readme` file.

## Credentials

- **Username:** `bandit18`
- **Password:** `x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`

## Connection

The normal SSH connection command is:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220
```

However, this level has a special restriction that prevents normal interactive access.

## Hints & Commands Learned

- `ssh`
- Remote command execution
- SSH command-line options
- Non-interactive SSH sessions

## Steps to Solve

### Step 1: Attempt a normal SSH connection

Try connecting using the standard SSH command:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220
```

After authentication, the session displays a message and terminates.

This happens because the account is configured to log out users when they attempt to start an interactive shell.

### Step 2: Execute a command directly through SSH

Instead of requesting an interactive shell, execute the `cat` command remotely:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```

**Explanation:**

- `ssh` establishes the remote connection.
- `bandit18@bandit.labs.overthewire.org` specifies the remote username and server.
- `-p 2220` specifies the SSH port.
- `cat readme` is the command executed on the remote server.

The command runs without starting an interactive shell and displays the contents of `readme`.

### Step 3: Retrieve the next password

Read the output returned by the remote command. It contains the password required for the next level.

## Next Level Password

```text
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```

## Commands Summary

| Command | Purpose |
|---|---|
| `ssh` | Establish a secure remote connection |
| `ssh user@host command` | Execute a command on a remote server without opening an interactive shell |
| `cat readme` | Display the contents of the remote `readme` file |

## Key Takeaway

SSH can execute remote commands without starting an interactive shell.

This is useful when an account restricts interactive access but still permits specific remote command execution.

The important lesson is that an SSH connection does not always need to provide a shell. You can execute a command directly by placing it after the connection details.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [OpenSSH Manual – ssh](https://man.openbsd.org/ssh)

---

*This writeup documents the commands and solution steps used for the Bandit Level 18 → Level 19 challenge.*
