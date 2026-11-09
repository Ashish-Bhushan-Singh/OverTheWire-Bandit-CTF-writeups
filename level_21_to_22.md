# Bandit Level 21 → Level 22

**Updated:** 9 November 2026

## Credentials

- **Username:** `bandit21`
- **Password:** `EeoULMCra2q0dSkYj561DX7s1CpBuOBt`

## Connection

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `cd`
- `cat`
- Cron jobs
- Scheduled task execution
- Shell scripts

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit21` using SSH:

```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Navigate to the cron configuration directory

```bash
cd /etc/cron.d
```

This directory contains configuration files for scheduled cron jobs.

### Step 3 – Inspect the Bandit 22 cron configuration

```bash
cat cronjob_bandit22
```

The cron entry uses this schedule:

```text
* * * * *
```

The five asterisks represent:

1. Minute
2. Hour
3. Day of the month
4. Month
5. Day of the week

When all five fields contain `*`, the job is scheduled to run every minute.

### Step 4 – Inspect the script executed by the cron job

```bash
cat /usr/bin/cronjob_bandit22.sh
```

Reading this script helps identify what the scheduled task does and where it writes its output.

### Step 5 – Read the password file

Use the temporary file path identified from the script:

```bash
cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
```

The file contains the password for Bandit Level 22.

### Step 6 – Save the next-level password

Use the retrieved password to log in as `bandit22`.

## Next Level Password

```text
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```

## Key Learning Points

- Cron is a Linux service used to schedule commands and scripts.
- `/etc/cron.d` contains system-wide cron job configuration files.
- The five-field cron expression `* * * * *` schedules a task every minute.
- Cron jobs can execute shell scripts automatically.
- Inspecting a scheduled script can reveal where it writes information.
