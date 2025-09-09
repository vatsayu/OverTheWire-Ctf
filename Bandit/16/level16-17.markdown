# Bandit Level 16 → 17

## Objective
Compare two password files to find the password for `bandit17`.

## Solution
Use the `diff` command to compare files:

```bash
diff passwords.new passwords.old
```

The output shows the differing line: `< x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`.

## Password for bandit17
x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO