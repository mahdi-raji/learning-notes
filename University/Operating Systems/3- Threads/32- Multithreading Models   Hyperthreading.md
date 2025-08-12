## Types of Threads

### User Threads
- Supported above the kernel.
- Managed without direct kernel support.

### Kernel Threads
- Fully supported and managed directly inside the kernel.

---

## Multithreading Models

This refers to the type of relationship that can exist between **user threads** and **kernel threads**.

### Many-to-One
- Many user threads are mapped to a single kernel thread.
- Limitation: If one user thread blocks, all others are blocked.

![Many-to-One](attachments/Pasted%20image%2020250812194251.png)

---

### One-to-One
- Each user thread is mapped to its own kernel thread.
- More concurrency than Many-to-One, but may require more overhead.

![One-to-One](attachments/Pasted%20image%2020250812194604.png)

---

### Many-to-Many
- Many user threads are mapped to many kernel threads.
- The number of kernel threads is smaller than or equal to the number of user threads.
- Example: 4 user threads may be mapped to 4 or fewer kernel threads.
- Often considered the **best model** due to flexibility.

![Many-to-Many](attachments/Pasted%20image%2020250812194934.png)

---

## Hyperthreading

### SMT (Simultaneous Multithreading)
- More than one thread is executed simultaneously within the same physical processor.
- The processor contains multiple cores.
- Each core is virtually divided to handle multiple threads at once.
- Example: In a dual-core CPU, hyperthreading allows each core to run two threads, making the system appear as having 4 logical processors.
![Hyperthreading](attachments/Pasted%20image%2020250812195455.png)
### How a Core is "Split" Virtually
- A core has several **execution units**:
  - **ALU** → integer calculations  
  - **FPU** → floating-point calculations  
  - **Load/Store Unit** → memory operations  
  - **Branch Unit** → conditional checks  
- During execution, some units may be **idle**.  
- Hyperthreading allows another thread to use those idle units by maintaining **separate register sets** for each thread while sharing execution units.  

---

### Example: When Hyperthreading Helps
- **Thread A:** Reading data from RAM (Load/Store Unit)  
- **Thread B:** Integer math (ALU)  
→ While Thread A waits for RAM, Thread B uses ALU → **less idle time, better throughput**.  

---

### Example: When It Helps Less
- **Thread A:** Heavy floating-point math (FPU)  
- **Thread B:** Graphics math (FPU)  
→ Both need FPU → must take turns → **slower per thread**, small overall gain.  


  
![SMT](attachments/Pasted%20image%2020250812195759.png)
