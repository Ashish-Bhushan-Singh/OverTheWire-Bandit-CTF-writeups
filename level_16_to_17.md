# Bandit Level 16 → Level 17

**Date:** 7 November 2026

## Objective

Find the correct service listening on a port between `31000` and `32000` on localhost.

Identify the available ports, test the services using SSL/TLS, and retrieve the credentials required for the next level.

## Credentials

- **Username:** `bandit16`
- **Password:** `kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx`

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `nmap`
- `ncat`
- Port scanning
- TCP services
- SSL/TLS connections
- SSH private key authentication

## Steps to Solve

### Step 1: Connect to the Bandit server

Use the SSH command above with the supplied credentials.

### Step 2: Scan the port range

Use Nmap to identify open ports on localhost between `31000` and `32000`:

```bash
nmap localhost -p 31000-32000
```

**Explanation:**

- `nmap` is a network scanning utility.
- `localhost` specifies the local machine.
- `-p 31000-32000` specifies the port range to scan.

The scan displays the ports that are open and accepting connections.

### Step 3: Test the open ports using SSL/TLS

Use Ncat with its SSL option to connect to each open port:

```bash
ncat --ssl localhost <port>
```

Replace `<port>` with an actual open port discovered in Step 2.

Submit the current `bandit16` password when prompted.

Some services may simply return the submitted text. Continue testing the discovered ports until you find the service that provides the next level's credentials.

### Step 4: Retrieve the next level's RSA private key

The correct service returns an RSA private key for the next level.

Copy the complete key into a file on your local machine. Preserve the original line breaks and the `BEGIN` and `END` markers.

For security reasons, do not include the actual private key in this public GitHub writeup.

### Step 5: Protect the private key

Set restrictive permissions on the local private key file:

```bash
chmod 600 private_key.txt
```

This allows only the file owner to read and write the key.

### Step 6: Connect to the next level

Use the private key to authenticate as `bandit17`:

```bash
ssh -i private_key.txt bandit17@bandit.labs.overthewire.org -p 2220
```

If authentication succeeds, you have access to the next level.

## Next Level Password

```text
EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
```

## Next Level RSA Key

The RSA private key was returned by the correct SSL/TLS service.

**Security note:** Keep the private key in a protected local file. Never commit it to a public GitHub repository.

## Commands Summary

| Command | Purpose |
|---|---|
| `nmap` | Scan hosts and identify open ports |
| `nmap localhost -p 31000-32000` | Scan the specified local port range |
| `ncat --ssl` | Establish an SSL/TLS connection |
| `chmod 600` | Restrict private key file permissions |
| `ssh -i` | Authenticate using a specified private key |

## Key Takeaway

This challenge demonstrates a practical network enumeration workflow:

1. Scan a range of ports using Nmap.
2. Identify open services.
3. Test services using SSL/TLS with Ncat.
4. Retrieve the required RSA private key.
5. Use SSH key-based authentication to access the next level.

It introduces the importance of combining port scanning, service interaction, and secure authentication.

## References

- [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [Nmap Reference Guide](https://nmap.org/book/man.html)
- [Ncat Reference Guide](https://nmap.org/ncat/)
- [OpenSSH Manual](https://man.openbsd.org/ssh)

---

*This writeup documents the commands and solution approach used for the Bandit Level 16 → Level 17 challenge.*
