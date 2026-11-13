# Bandit Level 26 → Level 27

**Updated:** 13 November 2026

## Credentials

- **Username:** `bandit26`
- **Password:** `NOT FOUND!` (not independently retrieved)

## Connection

Continue from the shell access obtained during Level 25 → 26.

The SSH private key used in the previous challenge provides access to the Bandit 26 environment:

```bash
ssh -i bandit26.sshkey bandit26@localhost -p 2220
```

## Hints & Commands Learned

- `ssh`
- `ls`
- `./` (executing a program)
- Setuid binaries
- `cat`

## Steps to Solve

### Step 1 – Access the Bandit 26 environment

Continue using the shell access obtained in the previous challenge.

### Step 2 – List the files

Run:

```bash
ls -la
```

This displays the files in the current directory, including hidden files.

### Step 3 – Locate the `bandit27-do` executable

Look for the executable named:

```text
bandit27-do
```

This is a special program that allows the user to execute a command with the privileges of its owner.

### Step 4 – Execute the program to read the Bandit 27 password

Run:

```bash
./bandit27-do cat /etc/bandit_pass/bandit27
```

**Command explanation:**

- `./bandit27-do` executes the program in the current directory.
- `cat` is the command passed to the program.
- `/etc/bandit_pass/bandit27` is the password file for Bandit Level 27.

The executable runs the supplied command with the privileges of its owner, allowing access to the Bandit 27 password file.

### Step 5 – Save the next-level password

Use the retrieved password to log in as `bandit27`.

## Next Level Password

```text
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

## Key Learning Points

- `ls -la` displays all directory entries, including hidden files.
- `./` executes a program from the current directory.
- Setuid executables can run with the effective user ID of their owner.
- A specially configured executable can allow controlled execution of commands with another user's privileges.
- `cat` can read files when the executing process has sufficient permissions.
