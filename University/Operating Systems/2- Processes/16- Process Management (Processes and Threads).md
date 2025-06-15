
## How a Program Is Developed and Executed

### 1. Writing the Program

- A program is initially written in a **high-level programming language** (e.g., C, Python).
- However, a computer only understands **binary (machine) code**.
- So the high-level program must be **translated into binary code** using a **compiler** or **interpreter**.

> 🧠 Note: Compilation creates an executable file (e.g., `.exe`), but just having the binary code is not enough for execution.

---

### 2. Loading the Program

- To **execute** the binary, it must be **loaded into memory**.
- Additionally, the program needs **resources** (e.g., CPU time, memory space, I/O devices).
- The **Operating System (OS)** is responsible for:
  - Loading the program into memory.
  - Allocating necessary resources.
  - Managing execution.

---

### 3. Process

- A **process** is a **program in execution**.
- It includes:
  - The program code (binary).
  - The current activity (Program Counter, registers).
  - Resources like open files, memory, and I/O.

> 📌 Example: When you open **Chrome**, multiple **processes** may be created for tabs, extensions, etc.

![Multiple Chrome Processes](attachments/Pasted%20image%2020250615194103.png)

---

### 4. Thread

- A **thread** is the **basic unit of CPU execution** within a process.
- A **process** can contain:
  - Just one thread (single-threaded).
  - Or **many threads** (multi-threaded), all sharing the same memory and resources.

> 🧵 Threads allow multiple operations to run in parallel within the same process.

![Thread View in Process Explorer](attachments/Pasted%20image%2020250615194252.png)

---

### 5. Visualizing Execution

- Tools like **Process Explorer** can show:
  - Active **processes** and their **associated threads**.
  - Useful for debugging or understanding execution flow.

![Program to Process Diagram](attachments/Pasted%20image%2020250615193902.png)
