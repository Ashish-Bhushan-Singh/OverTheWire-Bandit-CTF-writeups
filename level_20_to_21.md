# Bandit Level 20 → Level 21

**Updated:** 7 November 2026

## Credentials

- **Username:** `bandit20`
- **Password:** `0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`

## Connection

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `echo`
- `nc` (Netcat)
- Setuid binaries
- Background processes (`&`)
- `-n` option to prevent a trailing newline

## Steps to Solve

### Step 1 – Connect to the Bandit server

Use SSH to log in as `bandit20`:

```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Start a Netcat listener

In the Bandit 20 shell, start a listener on port `10000` and send the current level's password through it:

```bash
echo -n "0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO" | nc -l -p 10000 &
```

**Explanation:**

- `echo -n` prints the password without adding a newline.
- `nc -l -p 10000` listens for an incoming connection on port `10000`.
- `&` runs the listener in the background so the terminal remains available.

You can use another available port if needed, provided you use the same port in the next command.

### Step 3 – Run the `suconnect` program

Execute:

```bash
./suconnect 10000
```

The `suconnect` program connects to the listener on the specified port and checks the password it receives. When the supplied password is correct, it returns the password for Bandit Level 21.

### Step 4 – Save the next-level password

Use the returned password to log in as `bandit21`.

## Next Level Password

```text
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```

## Key Learning Points

- Netcat can listen for incoming network connections and send data through them.
- The `&` operator runs a process in the background.
- The `-n` option prevents `echo` from appending a newline.
- Setuid programs can execute with the effective privileges of their file owner, subject to the program's implementation and permissions.
