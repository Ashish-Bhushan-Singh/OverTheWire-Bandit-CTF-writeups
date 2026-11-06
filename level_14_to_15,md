# Bandit Level 14 → Level 15

**Date:** 6 November 2026

## Objective

Retrieve the next level's password by connecting to a service running locally on TCP port `30000` and submitting the current level's password.

## Credentials

- **Username:** `bandit14`
- **Password:** `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `nc` (Netcat)
- TCP connections
- Localhost (`127.0.0.1`)
- Network ports
- Client-server communication

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Connect to the local service

Run the following command:

```bash
nc localhost 30000
```

**Explanation:**

- `nc` starts the Netcat utility.
- `localhost` refers to the same machine where the command is running.
- `30000` is the TCP port of the service.

Netcat establishes a connection to the service listening on that port.

### Step 3: Submit the current level's password

Copy the current `bandit14` password:

```text
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

Paste it into the Netcat connection and press **Enter**.

### Step 4: Receive the next password

The service checks the submitted password and returns the password for the next level if the submission is correct.

### Step 5: Retrieve the next password

Save the returned password and use it to access the next Bandit level.

## Next Level Password

```text
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

## Commands Summary

| Command | Purpose |
|---|---|
| `nc` | Start a Netcat connection |
| `nc localhost 30000` | Connect to TCP port 30000 on the local machine |

## Key Takeaway

Netcat is a command-line networking tool that can establish connections to services listening on specific ports.

In this challenge, we used it to communicate with a local TCP service and submit a password. This is a useful introduction to understanding how clients communicate with network services.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [Netcat Manual](https://man.openbsd.org/nc)

---

*This writeup documents the commands and solution steps used for the Bandit Level 14 → Level 15 challenge.*
