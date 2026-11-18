# Bandit Level 32 → Level 33

**Updated:** 18 November 2026

## Credentials

- **Username:** `bandit32`
- **Password:** `3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K`

## Connection

```bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `ssh`
- `$0`
- `whoami`
- `cat`
- Restricted shells
- Shell escape techniques

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit32`:

```bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
```

After connecting, you are placed inside a restricted environment called the **UPPERCASE SHELL**.

Commands entered in this shell are converted to uppercase, making normal command execution difficult.

### Step 2 – Escape the uppercase shell

Run:

```bash
$0
```

`$0` is a special shell variable that represents the name or invocation of the current shell.

In this challenge, executing it starts another shell and allows you to escape the uppercase command restriction.

### Step 3 – Verify the current user

Run:

```bash
whoami
```

The output identifies the current user as:

```text
bandit33
```

This confirms that you have reached the Bandit 33 environment.

### Step 4 – Read the Bandit 33 password

Run:

```bash
cat /etc/bandit_pass/bandit33
```

The command displays the password for Bandit Level 33.

### Step 5 – Save the final password

The retrieved password is:

## Next Level Password

```text
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
```

## Key Learning Points

- Restricted shells can limit which commands a user can execute.
- `$0` represents the current shell's invocation name.
- Executing `$0` can start another shell in environments where the current shell permits it.
- `whoami` identifies the current effective user.
- Understanding shell behavior can help investigate and escape restricted environments.
