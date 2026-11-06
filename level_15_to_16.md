# Bandit Level 15 → Level 16

**Date:** 6 November 2026

## Objective

Retrieve the next level's password by connecting to a local service on TCP port `30001` using SSL/TLS and submitting the current level's password.

## Credentials

- **Username:** `bandit15`
- **Password:** `8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `ncat`
- SSL/TLS
- Encrypted network connections
- TCP ports
- Localhost (`127.0.0.1`)

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Connect to the local SSL/TLS service

Run the following command:

```bash
ncat --ssl localhost 30001
```

**Explanation:**

- `ncat` is a networking utility included with Nmap.
- `--ssl` enables SSL/TLS encryption for the connection.
- `localhost` refers to the same machine where the command is running.
- `30001` is the TCP port of the service.

Unlike the previous challenge, this service expects an encrypted SSL/TLS connection.

### Step 3: Submit the current level's password

Copy the current `bandit15` password:

```text
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

Paste it into the active Ncat connection and press **Enter**.

### Step 4: Receive the next password

The service verifies the submitted password and returns the next level's password when the authentication succeeds.

### Step 5: Retrieve the next password

Save the returned password and use it to access the next Bandit level.

## Next Level Password

```text
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

## Commands Summary

| Command | Purpose |
|---|---|
| `ncat` | Establish a network connection |
| `ncat --ssl` | Establish an SSL/TLS-encrypted connection |
| `ncat --ssl localhost 30001` | Connect securely to the local service on TCP port 30001 |

## Key Takeaway

Not all network services accept plain-text connections. Some require SSL/TLS to encrypt communication between the client and server.

In this challenge, we used Ncat with the `--ssl` option to establish an encrypted connection and submit the password securely.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [Ncat Reference Guide](https://nmap.org/ncat/)

---

*This writeup documents the commands and solution steps used for the Bandit Level 15 → Level 16 challenge.*
