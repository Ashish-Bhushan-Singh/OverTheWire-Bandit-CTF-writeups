# Bandit Level 3 → Level 4

**Platform:** OverTheWire Bandit  
**Level:** 3 → 4  
**Date:** 1 November 2026

---

## Objective

The objective of this level is to locate and retrieve the password for the next level.

The password is stored in a hidden file inside a directory named `inhere`.

This challenge introduces directory navigation and identifying hidden files in Linux.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit3` |
| Password | `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

Enter the password for `bandit3` when prompted.

## Steps to Solve

**Step 1 — Connect to the server**

Establish an SSH connection to the Bandit environment.

**Step 2 — Navigate to the target directory**

Use `cd` to enter the `inhere` directory.

```bash
cd inhere
```

**Step 3 — List hidden files**

Run:

```bash
ls -la
```

The `-a` option displays hidden directory entries, including filenames beginning with a dot.

**Step 4 — Identify the hidden file**

Locate the file named:

```text
...Hiding-From-You
```

**Step 5 — Read the file**

Use `cat` to display its contents.

```bash
cat ...Hiding-From-You
```

**Step 6 — Retrieve the next-level password**

The file contents provide the password required to log in as `bandit4`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `cd` | Change the current working directory |
| `ls -la` | Display all directory entries, including hidden files |
| `cat` | Display file contents |

## Key Takeaways

- Learned how to navigate directories using `cd`.
- Understood how to list hidden files using `ls -a`.
- Practiced locating files with unusual names.
- Learned how to retrieve information from hidden files.
- Improved familiarity with Linux directory navigation.

## Next Level Password

```text
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

---

**Previous Level:** [Bandit Level 2 → Level 3](./level_2_to_3.md)

**Next Level:** [Bandit Level 4 → Level 5](./level_4_to_5.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
