# Bandit Level 1 → Level 2

**Platform:** OverTheWire Bandit  
**Level:** 1 → 2  
**Date:** 1 November 2026

---

## Objective

The objective of this level is to retrieve the password for the next level.

The password is stored in a file named `-` in the home directory.

Since the filename consists of a single hyphen, using `cat -` directly can cause the shell command to interpret it as standard input rather than a filename.

We can solve this by explicitly specifying the file path.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit1` |
| Password | `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

Enter the password for `bandit1` when prompted.

## Steps to Solve

**Step 1 — Connect to the server**

Establish an SSH connection to the Bandit environment.

**Step 2 — Identify the unusual filename**

The password is stored in a file named:

```text
-
```

A filename consisting only of a hyphen can be interpreted as a special argument by some commands.

**Step 3 — Read the file**

Use `./` to explicitly identify the file in the current directory.

```bash
cat ./-
```

**Step 4 — Retrieve the next-level password**

The command displays the contents of the file, which contains the password for `bandit2`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `cat` | Display file contents |
| `./` | Refer to a file or executable in the current directory |

## Key Takeaways

- Learned how to handle filenames containing special characters.
- Understood why a standalone hyphen can be interpreted as an option or standard input.
- Learned to use `./` to explicitly reference a file in the current directory.
- Practiced reading files using `cat`.

## Next Level Password

```text
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

---

**Previous Level:** [Bandit Level 0 → Level 1](./level_0_to_1.md)

**Next Level:** [Bandit Level 2 → Level 3](./level_2_to_3.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
