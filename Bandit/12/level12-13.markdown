# Bandit Level 12 → 13

## Objective
Retrieve the password for `bandit13` from `data.txt`, a hexdump of a repeatedly compressed file.

## Solution
The file requires multiple compression and decompression steps:

1. Create a temporary directory: `mkdir /tmp/dedsec`
2. Copy the data file: `cp data.txt /tmp/dedsec`
3. Convert hex to binary: `xxd -r data.txt > data`
4. Rename to gzip: `mv data file.gz`
5. Decompress gzip: `gzip -d file.gz`
6. Check file type (bzip2): `file file`
7. Decompress bzip2: `bzip2 -d file.bz2`
8. Rename to gzip (after identifying with `file`).
9. Identify as POSIX tar archive.
10. Rename to tar: `mv file file.tar`
11. Extract tar: `tar xvf file.tar`
12. Repeat for nested files (e.g., rename `data5.bin` to `data.tar`, extract again).
13. Continue decompressing with tar and gzip until an ASCII text file is obtained.
14. Read the final file to find the password.

## Password for bandit13
FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn