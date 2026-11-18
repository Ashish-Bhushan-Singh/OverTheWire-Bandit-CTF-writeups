# Bandit Level 31 → Level 32

**Updated:** 18 November 2026

## Credentials

- **Username:** `bandit31`
- **Password:** `fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy`

## Connection

```bash
ssh bandit31@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `git`
- `git clone`
- `echo`
- `git add`
- `git commit`
- `git push`
- `.gitignore`
- Git staging and remote repositories

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit31`:

```bash
ssh bandit31@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Clone the Git repository

Create a temporary working directory and clone the repository, following the same process used in the previous Git challenges:

```bash
mktemp -d
cd /tmp/<your-created-directory>
git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
cd repo
```

Enter the current Bandit 31 password when prompted.

### Step 3 – Inspect the README file

```bash
cat README.md
```

The README explains that the challenge requires us to create and push a file named `key.txt` containing:

```text
May I come in?
```

### Step 4 – Create the required file

Run:

```bash
echo "May I come in?" > key.txt
```

This creates `key.txt` and writes the required text into it.

### Step 5 – Inspect and modify `.gitignore`

Check the contents of `.gitignore`:

```bash
cat .gitignore
```

The pattern `*.txt` prevents Git from tracking text files.

Open the file:

```bash
vim .gitignore
```

Remove the `*.txt` rule, then save and exit.

This allows Git to track `key.txt`.

### Step 6 – Stage and commit the file

Add the required file:

```bash
git add key.txt
```

Create a commit:

```bash
git commit -m "May I come in?"
```

### Step 7 – Push the commit to the remote repository

Run:

```bash
git push
```

Git sends the commit to the remote repository. The challenge service checks the pushed content and returns the password for Bandit Level 32.

### Step 8 – Save the next-level password

Use the retrieved password to log in as `bandit32`.

## Next Level Password

```text
3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```

## Key Learning Points

- `echo` can create a file and write text into it.
- `.gitignore` specifies files and patterns Git should ignore.
- `git add` stages files for a commit.
- `git commit` records staged changes.
- `git push` sends local commits to a remote repository.
- Git may ignore files even when they exist in the working directory.
- Understanding `.gitignore` is important when troubleshooting files that are not being tracked.
