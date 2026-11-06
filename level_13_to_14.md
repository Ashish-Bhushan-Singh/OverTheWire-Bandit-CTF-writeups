# Bandit Level 13 → Level 14

**Date:** 6 November 2026

## Objective

Access the next Bandit level using an RSA private key instead of a password.

The private key is provided in the current level's home directory. We need to copy it to our local machine, set secure file permissions, and use SSH authentication with that key.

## Credentials

- **Username:** `bandit13`
- **Password:** `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`

## Connection

Connect to the Bandit server:

```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `cat`
- `ssh`
- `ssh -i`
- `chmod`
- RSA private keys
- SSH key-based authentication
- Linux file permissions

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Read the RSA private key

Display the private key file:

```bash
cat sshkey.private
```

The output contains an RSA private key, including its `BEGIN` and `END` markers.

### Step 3: Copy the private key to your local machine

Create a file named `private_key.txt` on your local machine:

```bash
vim private_key.txt
```

Copy the complete contents of `sshkey.private` into this file.

Make sure the private key is copied correctly, including the beginning and ending markers, with the original line breaks preserved.

**Security note:** Do not publish the private key in a public GitHub repository. Keep it in a secure local location.

### Step 4: Set secure file permissions

Restrict access to the private key:

```bash
chmod 600 private_key.txt
```

**Explanation:**

- `chmod` changes file permissions.
- `600` gives the file owner read and write permissions.
- Group members and other users receive no permissions.

SSH may reject a private key if its permissions are too open.

### Step 5: Connect to the next level using the private key

Use SSH's `-i` option to specify the private key:

```bash
ssh -i private_key.txt bandit14@bandit.labs.overthewire.org -p 2220
```

**Explanation:**

- `-i` specifies the identity file (private key).
- `private_key.txt` is the local private key file.
- `bandit14` is the username for the next level.
- `-p 2220` specifies the SSH port.

If authentication succeeds, you will gain access to the `bandit14` account.

## Next Level Password

```text
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```

## Next Level RSA Key

The RSA private key was obtained from `sshkey.private` during this challenge.

**Do not include the actual private key in this public writeup.** Keep it in a protected local file if you need it for your lab work.

## Commands Summary

| Command | Purpose |
|---|---|
| `cat sshkey.private` | Display the RSA private key |
| `vim private_key.txt` | Create a local file and paste the private key |
| `chmod 600 private_key.txt` | Restrict access to the private key |
| `ssh -i` | Authenticate using a specified private key |
| `ssh -p 2220` | Connect using the specified SSH port |

## Key Takeaway

SSH supports authentication using cryptographic key pairs.

A private key can be used to authenticate to a remote server without entering the account password. Protecting the private key with appropriate file permissions is an important part of secure SSH usage.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [OpenSSH Manual – ssh](https://man.openbsd.org/ssh)
- [OpenSSH Manual – ssh-keygen](https://man.openbsd.org/ssh-keygen)

---

*This writeup documents the commands and solution steps used for the Bandit Level 13 → Level 14 challenge.*
