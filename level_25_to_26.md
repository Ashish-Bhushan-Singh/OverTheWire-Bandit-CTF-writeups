# Bandit Level 25 → Level 26

**Updated:** 13 November 2026

## Credentials

- **Username:** `bandit25`
- **Password:** `iCi86ttT4KSNe1armKiwbQNmB3YJP3q4`

## Connection

```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `ssh`
- SSH private keys
- Terminal resizing
- `more` pager
- Vim-like commands
- Shell escape

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit25`:

```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Attempt to connect to Bandit 26

Use the SSH private key provided in the Bandit 25 home directory:

```bash
ssh -i bandit26.sshkey bandit26@localhost -p 2220
```

The login starts a restricted environment that displays a short text through the `more` pager instead of providing a normal shell.

### Step 3 – Reduce the terminal height

Resize the terminal window to make it very small.

The short text should no longer fit completely on the screen. This causes the `more` pager to remain active and gives you an opportunity to interact with it.

### Step 4 – Enter the pager's command mode

While the pager is active, press:

```text
v
```

This opens the text in Vim.

Inside Vim, enter the following command:

```vim
:set shell=/bin/bash
```

Then execute:

```vim
:shell
```

This opens a Bash shell from the pager's editor environment.

### Step 5 – Continue to Bandit Level 26

You now have access to a shell in the Bandit 26 environment.

The next challenge is to use this access to retrieve the Bandit 26 password.

## Next Level Password

**Status:** Not found yet.

The Bandit 26 password has not been retrieved at this stage. Do not mark this level as fully completed until the password is obtained and verified.

## Key Learning Points

- SSH can authenticate using a private key with the `-i` option.
- SSH sessions can launch restricted programs instead of a normal shell.
- Terminal dimensions can affect how terminal-based programs behave.
- `more` is a pager used to display text one screen at a time.
- Vim supports commands that can launch an external shell.
- Understanding how programs interact can help investigate unusual login environments.
