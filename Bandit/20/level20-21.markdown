# Bandit Level 20 → 21

## Objective
Set up a listener to send the `bandit20` password to a service and retrieve the password for `bandit21`.

## Solution
1. In one terminal, set up a listener:
   ```bash
   cat /etc/bandit_pass/bandit20 | nc -l 1234
   ```
2. In another terminal, connect to the listener:
   ```bash
   ./suconnect 1234
   ```

This retrieves the next password.

## Password for bandit21
EeoULMCra2q0dSkYj561DX7s1CpBuOBt