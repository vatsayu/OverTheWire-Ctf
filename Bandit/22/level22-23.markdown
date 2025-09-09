# Bandit Level 22 → 23

## Objective
Retrieve the password for `bandit23` by generating a hash-based filename.

## Solution
Set a variable and generate a hash to locate the password file:

```bash
myname=bandit123
echo $myname | md5sum | cut -d ' ' -f1
cat /tmp/<generated_hash>
```

## Password for bandit23
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga