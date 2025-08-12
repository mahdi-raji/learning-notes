## fork and exec (Linux/Unix)

### fork()
- Duplicates the calling process → creates a **child process**.
- The original process is called the **parent**, the copy is the **child**.
- Parent and child have **different process IDs**.
- Both start execution **from the same point** (the next instruction after `fork()`).

**How it works step-by-step (example with 3 forks):**
1. First `fork()` → only 1 parent exists, creates 1 child → total **2 processes**.
2. Second `fork()` → each of the 2 processes creates 1 child → total **4 processes**.
3. Third `fork()` → each of the 4 processes creates 1 child → total **8 processes**.

**Formula for total processes after N forks:**  
```
Total = 2^N processes
Newly created processes = 2^N - 1
```

![Example 1](attachments/Pasted%20image%2020250812212521.png)  
![Example 2](attachments/Pasted%20image%2020250812212655.png)

---

### exec()
- **Replaces** the current process image with a **new program**.
- The **PID stays the same** because it’s the same process — only the content/code changes.
- It does **not "jump" to another program** like a function call; instead, the old program is completely replaced in memory.
- After `exec()`, execution starts from the **entry point of the new program**, and the old code is gone.
- Often used **after `fork()`** to make the child process run a different program.

**Example:**
- Program calls `exec()` to run **ex2**.
- Output shows: same PID as before, but now the process runs the code of **ex2**.

![Exec Example](attachments/Pasted%20image%2020250812213244.png)
