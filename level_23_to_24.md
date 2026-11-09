# Bandit Level 23 → Level 24

**Updated:** 9 November 2026

## Credentials

- **Username:** `bandit23`
- **Password:** `0Zf11ioIjMVN551jX3CmStKLYqjk54Ga`

## Connection

```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `cd`
- `cat`
- `vim`
- Cron jobs
- Shell scripting
- `chmod`
- File permissions

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit23`:

```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Inspect the scheduled cron script

Read the Bandit 24 cron script:

```bash
cat /usr/bin/cronjob_bandit24.sh
```

Inspecting the script helps explain how files placed in the designated spool directory are processed by the cron job.

### Step 3 – Create a shell script

Create a new script in the directory monitored by the cron job:

```bash
vim /var/spool/bandit24/foo/foo.txt
```

Add the following content:

```bash
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/bandit24pass
```

Save and exit the editor.

### Step 4 – Make the script executable

The cron job needs to execute the script, so change its permissions:

```bash
chmod +x /var/spool/bandit24/foo/foo.txt
```

### Step 5 – Wait for the cron job to execute

The scheduled job periodically processes executable scripts placed in its monitored directory. Wait for it to run.

The script executes with the privileges of `bandit24` and writes the Bandit 24 password to:

```text
/tmp/bandit24pass
```

### Step 6 – Read the password

Once the cron job has executed the script, read the output file:

```bash
cat /tmp/bandit24pass
```

The output contains the password for Bandit Level 24.

### Step 7 – Save the next-level password

Use the retrieved password to log in as `bandit24`.

## Next Level Password

```text
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
```

## Key Learning Points

- Cron jobs can automatically execute scripts at scheduled intervals.
- A script needs execute permission to run as a program.
- `chmod +x` adds execute permission.
- A script executed by a privileged account can access files that the current user cannot read directly.
- Output redirection (`>`) writes command output to a file.
- Temporary files in `/tmp` can be used to pass results between processes.
