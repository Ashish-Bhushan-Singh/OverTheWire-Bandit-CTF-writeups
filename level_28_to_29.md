# Bandit Level 28 → Level 29

**Updated:** 13 November 2026

## Credentials

- **Username:** `bandit28`
- **Password:** `Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN`

## Connection

```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `git`
- `git clone`
- `git log`
- `git reset`
- Git commit history
- Repository version control

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit28`:

```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Clone the Git repository

Create a temporary working directory and clone the repository, following the same process used in Level 27 → 28.

```bash
mktemp -d
cd /tmp/<your-created-directory>
git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
cd repo
```

Enter the current Bandit 28 password when prompted.

### Step 3 – Inspect the README file

```bash
cat README.md
```

The password is not visible in the current version of the README file.

This indicates that the information may have been changed or removed in an earlier or later version.

### Step 4 – Inspect the Git commit history

Run:

```bash
git log
```

This displays the repository's commit history, including commit IDs, authors, dates, and commit messages.

Look for the commit:

```text
f257900db7c134cb5224c91013817e76d18457e0
```

Commit message:

```text
add missing data
```

### Step 5 – Restore the earlier commit

Use the following command to reset the working directory to the identified commit:

```bash
git reset --hard f257900db7c134cb5224c91013817e76d18457e0
```

**Explanation:**

- `git reset` moves the current branch to the specified commit.
- `--hard` updates the working directory and staging area to match that commit.
- The repository now reflects the file contents from the selected historical version.

### Step 6 – Read the README file again

```bash
cat README.md
```

The earlier version of the README contains the password for Bandit Level 29.

### Step 7 – Save the next-level password

Use the retrieved password to log in as `bandit29`.

## Next Level Password

```text
4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```

## Key Learning Points

- Git stores a history of changes made to tracked files.
- `git log` displays previous commits.
- Commit IDs identify specific versions of a repository.
- `git reset --hard` restores the working directory and staging area to a selected commit.
- Information removed from the latest version of a file may still exist in earlier commits.
- Before using `git reset --hard`, remember that it can discard uncommitted changes.
