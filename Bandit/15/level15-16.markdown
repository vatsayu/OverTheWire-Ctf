# Bandit Level 15 → 16

## Objective
Connect to a service on `localhost:30001` using SSL to retrieve an RSA key, then use it to log in as `bandit16`.

## Solution
1. Connect with SSL: `nc --ssl localhost 30001`
2. Copy or download the RSA key.
3. Use the key to log in: `ssh -i <KEY> bandit16@bandit.labs.overthewire.org -p 2220`

## Password for bandit16
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx