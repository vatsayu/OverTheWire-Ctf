# Bandit Level 11 → 12

## Objective
Retrieve the password for `bandit12` from the file `data.txt`, which contains text encoded with ROT13.

## Solution
The password is stored in `data.txt` and is encoded using ROT13. To decode it, use the `tr` command to shift the alphabet by 13 positions:

```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m' or using rot13 decoder
```

This outputs the decoded password for the next level.

## Password for bandit12
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
