# Bandit Level 10 → 11

## Objective
Retrieve the password for `bandit11` from the file `data.txt` located in the home directory of `bandit10`.

## Solution
 This level involves decoding a base64-encoded string in `data.txt`. You can use the following command to decode it:

```bash
cat data.txt | base64 -d
```

This reveals the password for the next level.

## Password for bandit11
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
