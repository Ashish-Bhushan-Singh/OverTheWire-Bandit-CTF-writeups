# Bandit Level 0 → Level 1

**Platform:** OverTheWire Bandit  
**Level:** 0 → 1  
**Date:** 31 October 2026

---

## Objective

The goal of this level is to connect to the Bandit server using SSH and retrieve the password for the next level.

The password is stored in a file named `readme` in the home directory.

## Credentials

| Field | Value |
|---|---|
| Username | `bandit0` |
| Password | `bandit0` |
| SSH Port | `2220` |
| Host | `bandit.labs.overthewire.org` |

## Connection

Connect to the Bandit server using SSH:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

When prompted, enter the password:

```text
bandit0
```

## Steps to Solve

**Step 1 — Connect to the server**

Use SSH to establish a connection to the Bandit environment.

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

**Step 2 — Locate the password file**

The challenge provides a file named `readme` in the home directory.

**Step 3 — Read the file**

Use the `cat` command to display its contents.

```bash
cat readme
```

**Step 4 — Retrieve the next-level password**

The output contains the password required to log in as `bandit1`.

## Commands Learned

| Command | Purpose |
|---|---|
| `ssh` | Connect securely to a remote server |
| `cat` | Display the contents of a file |

## Key Takeaways

- Learned how to connect to a remote Linux machine using SSH.
- Understood how to specify a custom SSH port using `-p`.
- Learned to read file contents using `cat`.
- Retrieved the credentials required for the next Bandit level.

## Next Level Password

```text
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

---

**Previous Level:** None (Starting Level)

**Next Level:** [Bandit Level 1 → Level 2](./level_1_to_2.md)

**Official Challenge:** [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
