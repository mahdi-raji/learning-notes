# User Interface in Operating System

**User Interface** is something that allows the user to interact with the operating system.

![User Interface](attachments/Pasted%20image%2020250608071301.png)

---

## How Does the Command Line Perform?

![CLI Process](attachments/Pasted%20image%2020250608071530.png)

There are **two ways** the Command Line Interface (CLI) can perform commands:

### 1. CLI Contains the Code Inside the Task

- The CLI itself contains the code for certain basic operations.
- For example, when you enter the command `cd` (change directory), the command is built into the shell (like Bash), and no external program is executed.
- The CLI changes the current directory using its own internal logic.

### 2. CLI Calls an External Program

- The CLI does **not** contain the code itself.
- Instead, it **calls an external executable file** to perform the operation.
- For example, when you enter the command `ls` (list directory contents):
  - The shell (CLI) **parses** the command.
  - It **finds the `ls` executable** (usually located in `/bin/ls`).
  - It **runs that program** to show the directory listing.

> **Note:** Many common commands in UNIX/Linux like `ls`, `grep`, `cat`, etc. are **not built into the shell** — they are **external programs** that the CLI runs.