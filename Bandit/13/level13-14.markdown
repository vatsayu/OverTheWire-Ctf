# Bandit Level 13 → 14

## Objective
Use an SSH private key to log in as `bandit14` and retrieve the password.

## Solution
Use the provided SSH private key to connect:

```bash
ssh -l bandit14 -p 2220 -i sshkey.private localhost
```

After logging in, read the password from `/etc/bandit_pass/bandit14`.

## Password for bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS