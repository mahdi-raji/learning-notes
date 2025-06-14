
## Two Modes of Execution

Programs in a modern operating system can run in **two modes**:

- **User Mode**
- **Kernel Mode**

### ![User Mode vs Kernel Mode](attachments/Pasted%20image%2020250609223107.png)

---

## User Mode

- In **user mode**, programs **do not have direct access to hardware resources** like memory, disk, or CPU registers.
- This restriction ensures **isolation and protection**.
- Crashes in user mode **do not affect the entire system**, making it **safer**.

---

## Kernel Mode

- In **kernel mode**, programs (or more precisely, the OS kernel itself) **have full access to system resources**, including memory and hardware.
- A crash in kernel mode can result in a **complete system failure**.
- Only the **operating system** or its components are allowed to run in kernel mode.

---

##  System Calls and Mode Switching

In an operating system, **user-mode programs are not allowed to access critical system resources directly** (like memory, disk, or I/O devices).  
So when a program needs to **request a privileged service** from the OS, it must do so **indirectly** through a special interface called a:

### ➤ **System Call**

> A **System Call** is the mechanism that allows a user-mode program to **request services from the operating system kernel**.

This request causes a **mode switch** from **user mode** to **kernel mode**, allowing the OS to safely handle the operation.

---

### What Happens During a System Call:


1. The user-mode program issues a **system call** (e.g., `read()`, `write()`, `malloc()`).
2. The CPU performs a **context switch**:
   - It switches from **user mode** to **kernel mode**.
3. The OS (now running in kernel mode) executes the requested service.
4. Once the operation is completed, the OS:
   - Switches the CPU **back to user mode**.
   - Resumes the program where it left off.

### ![System Call Flow](attachments/Pasted%20image%2020250609223445.png)

> 🧠 **Real-life Analogy:**  
> Imagine user mode as a customer in a restaurant. The customer (program) can't enter the kitchen (kernel).  
> They place an order (system call), which is taken to the kitchen by a waiter (context switch).  
> The chef (kernel) prepares the food (requested operation) and sends it back via the waiter.


## 🧪 Example: System Call Sequence for a File Copy Program

This is a basic example of how a user-mode program uses **system calls** to copy data from one file to another.

Each interaction with the operating system (like reading from a file, writing to the screen, or opening a file) requires a **system call**, which triggers a **mode switch** from user mode to kernel mode.

---

### 🧾 Step-by-Step System Call Sequence

1. 📥 **Get the name of the input file**  
   - System Call: `read()` (acquire user input)

2. 🖥️ **Display prompt to screen**  
   - System Call: `write()` (write prompt like “Enter input file name:”)

3. ⌨️ **Accept user input**  
   - System Call: `read()` (get file name)

---

4. 📥 **Get the name of the output file**

5. 🖥️ **Display prompt**  
   - System Call: `write()` (e.g., “Enter output file name:”)

6. ⌨️ **Accept user input**  
   - System Call: `read()`

---

7. 📂 **Open the input file**  
   - System Call: `open()`

8. ❌ **Check if file exists**  
   - If not: **Abort** with error

9. 🆕 **Create the output file**  
   - System Call: `creat()` or `open()` with creation flag

10. ⚠️ **Check if output file already exists**  
   - If yes: **Abort** to prevent overwriting

### ![System Call Flow - File Operations](attachments/Pasted%20image%2020250609224454.png)

---

11. 🔁 **Copy Loop**  
    - **Read from input file**  
      - System Call: `read()`
    - **Write to output file**  
      - System Call: `write()`
    - Repeat until end of file or if read fails

12. 📁 **Close the output file**  
    - System Call: `close()`

13. ✅ **Write completion message**  
    - System Call: `write()` (e.g., “File copied successfully.”)

14. 🛑 **Terminate the program**  
    - System Call: `exit()`

### ![File Copy Sequence Diagram](attachments/Pasted%20image%2020250609224615.png)

> 🧠 **Note:** Every interaction with the OS — whether it's displaying a message, accepting input, opening/closing files — happens via **system calls**, ensuring safety and abstraction between user and kernel space.

