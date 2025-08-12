
### Thread Basics
- **Definition:** A thread is the basic unit of CPU utilization.
- **Components of a thread:**
  - **Program Counter** – Keeps track of the thread's execution point.
  - **Register Set** – Holds the thread's working data.
  - **Stack** – Stores function calls, local variables, and return addresses.
- **Shared Resources (within the same process):**
  - Code section
  - Data section
  - OS resources (e.g., files)

### Process and Threads
- **Traditional process:** Has a single thread of control.
- **Multithreaded process:** Has multiple threads of control, allowing multiple tasks to run at the same time.

> Example: In a Chrome browser process, some threads handle displaying the downloads page while others handle the actual file download.

---

### Single-Threaded vs. Multi-Threaded Process

![Single-threaded vs. Multi-threaded process](attachments/Pasted%20image%2020250812064348.png)

- **Single-threaded:** The process can run only one task at a time.
- **Multi-threaded:** Multiple threads can execute simultaneously, sharing the same code, data, and files.



![benetfits of mutli threaded:](attachments/Pasted%20image%2020250812065419.png)
 - **Utilization**
	Let’s say we have 4 processes.  
	If a process is single-threaded, it can only run on one processor.  
	But in a multi-threaded approach, each process can have several threads, and each of these threads can run on different processors at the same time.
### Process vs. Processor
A **Processor** (CPU) is the hardware that performs computations.  
A **Process** is a running program that can contain multiple threads.  

Each thread is executed by the operating system on the processors, and it doesn’t matter which process the thread belongs to — the processor simply receives instructions and executes them.  
This is why threads from different processes can run simultaneously on different processors, or even on the same processor (through time-slicing).
