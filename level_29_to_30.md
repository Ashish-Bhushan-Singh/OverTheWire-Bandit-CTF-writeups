# Bandit Level 29 → Level 30

**Updated:** 13 November 2026

## Credentials

- **Username:** `bandit29`
- **Password:** `4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7`

## Connection

```bash
ssh bandit29@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `git`
- `git clone`
- `git branch`
- `git switch`
- `git reset`
- Remote branches
- Detached HEAD state

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit29`:

```bash
ssh bandit29@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Clone the Git repository

Create a temporary working directory and clone the repository, following the same process used in the previous Git challenges:

```bash
mktemp -d
cd /tmp/<your-created-directory>
git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
cd repo
```

Enter the current Bandit 29 password when prompted.

### Step 3 – Inspect the README file

```bash
cat README.md
```

The password is not available in the current version of the README.

This suggests that another branch may contain different information.

### Step 4 – List the remote branches

Run:

```bash
git branch -r
```

This displays the remote branches available in the repository.

Look for the `origin/dev` branch.

### Step 5 – Switch to the development branch

Run:

```bash
git switch origin/dev
```

This checks out the remote development branch.

**Note:** Checking out `origin/dev` directly normally places Git in a detached HEAD state. This allows you to inspect that branch without creating a local tracking branch.

### Step 6 – Reset to the specified commit

Run:

```bash
git reset --hard 4a754d10ab4e0246b06b76cb0a561257a3b6bf22
```

This moves the current checkout to the specified commit and updates the working directory to match it.

### Step 7 – Read the README file

```bash
cat README.md
```

The README at the selected commit contains the password for Bandit Level 30.

### Step 8 – Save the next-level password

Use the retrieved password to log in as `bandit30`.

## Next Level Password

```text
qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```

## Key Learning Points

- Git repositories can contain multiple branches with different versions of files.
- `git branch -r` lists remote branches.
- `git switch` changes the current branch or checkout.
- Checking out a remote branch directly can result in a detached HEAD state.
- `git reset --hard` moves the current checkout to a specific commit and updates the working directory.
- Git history and branches can contain information that is not present in the default branch.
