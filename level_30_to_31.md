# Bandit Level 30 → Level 31

**Updated:** 13 November 2026

## Credentials

- **Username:** `bandit30`
- **Password:** `qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL`

## Connection

```bash
ssh bandit30@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `git`
- `git clone`
- `git tag`
- `git show`
- Git tags
- Repository inspection

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit30`:

```bash
ssh bandit30@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Clone the Git repository

Create a temporary working directory and clone the repository, following the same process used in the previous Git challenges:

```bash
mktemp -d
cd /tmp/<your-created-directory>
git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
cd repo
```

Enter the current Bandit 30 password when prompted.

### Step 3 – Inspect the README file

```bash
cat README.md
```

The password is not available in the current README file.

### Step 4 – List the Git tags

Run:

```bash
git tag
```

This displays the tags available in the repository.

Look for the tag named:

```text
secret
```

### Step 5 – Inspect the secret tag

Run:

```bash
git show secret
```

This displays the object referenced by the `secret` tag. In this challenge, the output reveals the password for Bandit Level 31.

### Step 6 – Save the next-level password

Use the retrieved password to log in as `bandit31`.

## Next Level Password

```text
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```

## Key Learning Points

- Git tags are references used to identify specific points in a repository's history.
- `git tag` lists the tags in a repository.
- `git show` displays information about a tag, commit, or other Git object.
- Important information may be stored in Git objects that are not visible in the current README file.
- Inspecting repository metadata can reveal information outside the current branch.
