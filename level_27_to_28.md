# Bandit Level 27 → Level 28

**Updated:** 13 November 2026

## Credentials

- **Username:** `bandit27`
- **Password:** `upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB`

## Connection

```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `git`
- `mktemp`
- `cd`
- `git clone`
- `cat`
- Repository navigation

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit27`:

```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Create a temporary working directory

Create a temporary directory:

```bash
mktemp -d
```

The command returns a directory path, for example:

```text
/tmp/tmp.XXXXXX
```

Use the actual path returned by your command and move into it:

```bash
cd /tmp/<your-created-directory>
```

### Step 3 – Clone the Git repository

Clone the repository provided by the challenge:

```bash
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
```

When prompted, enter the current Bandit 27 password.

This downloads a copy of the remote Git repository into a local directory named `repo`.

### Step 4 – Read the README file

Enter the repository directory or read the file directly:

```bash
cat repo/README
```

The README file contains the password for Bandit Level 28.

### Step 5 – Save the next-level password

Use the retrieved password to log in as `bandit28`.

## Next Level Password

```text
Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```

## Key Learning Points

- `mktemp -d` creates a temporary working directory.
- `git clone` copies a remote repository to your local environment.
- Git repositories can be accessed using SSH.
- `cat` displays the contents of a file.
- A repository's README file can contain useful information about the project.
