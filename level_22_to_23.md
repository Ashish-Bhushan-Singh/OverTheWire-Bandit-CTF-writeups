# Bandit Level 22 → Level 23

**Updated:** 9 November 2026

## Credentials

- **Username:** `bandit22`
- **Password:** `tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q`

## Connection

```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `cd`
- `cat`
- Cron jobs
- `echo`
- `md5sum`
- `cut`
- Command substitution: `$()`

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit22`:

```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Navigate to the cron configuration directory

```bash
cd /etc/cron.d
```

This directory contains configuration files for scheduled cron jobs.

### Step 3 – Inspect the Bandit 23 cron configuration

```bash
cat /etc/cron.d/cronjob_bandit23
```

The schedule uses:

```text
* * * * *
```

This means the job is scheduled to run every minute.

### Step 4 – Inspect the scheduled script

```bash
cat /usr/bin/cronjob_bandit23.sh
```

Read the script to understand how it generates the temporary filename and where it writes the password.

### Step 5 – Generate the temporary filename and read the password

The script uses an MD5 hash of the text `I am user bandit23` to generate the temporary filename.

Run:

```bash
cat /tmp/$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
```

**Command explanation:**

- `echo I am user bandit23` – Prints the specified text.
- `md5sum` – Calculates its MD5 hash.
- `cut -d ' ' -f 1` – Extracts the hash from the output.
- `$(...)` – Runs the commands inside and substitutes their output into the path.
- `cat` – Reads the file at the generated path.

The command displays the password stored in the temporary file.

### Step 6 – Save the next-level password

Use the retrieved password to log in as `bandit23`.

## Next Level Password

```text
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```

## Key Learning Points

- Cron jobs can run scripts automatically at scheduled intervals.
- `md5sum` generates an MD5 hash from input.
- `cut` extracts selected fields from command output.
- Command substitution with `$()` allows one command's output to be used as another command's argument.
- A script can generate a predictable temporary filename using a hash.
