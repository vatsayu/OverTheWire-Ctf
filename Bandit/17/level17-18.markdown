# Bandit Level 17 → 18

## Objective
Log in to `bandit18` using SSH with a forced pseudo-terminal to bypass restrictions.

## Solution
Use the `-t` flag to force a pseudo-terminal and run `/bin/sh`:

```bash
ssh -t bandit18@bandit.labs.overthewire.org -p 2220 /bin/sh
```

This logs you into a shell where you can read the `readme` file.

## Password for bandit18
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8