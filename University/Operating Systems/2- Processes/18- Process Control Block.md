## Process Control Block (PCB)

**PCB** is a data structure used by the Operating System to represent a process.

![PCB Structure](attachments/Pasted%20image%2020250615211320.png)

Each process has its own PCB that stores all the information required to manage and execute the process.

### Components of PCB

- **Process ID or Number**:  
  A unique identifier assigned to each process.

- **Process State**:  
  Represents the current state of the process (e.g., New, Ready, Running, Waiting, Terminated).

- **Program Counter**:  
  Holds the address of the next instruction to be executed for the process.

- **CPU Registers**:  
  Stores the contents of all the process-specific CPU registers. These are saved and restored during context switching.

- **CPU Scheduling Information**:  
  Includes the process's priority and pointers to scheduling queues. It helps the OS determine which process to run next.

- **Memory Management Information**:  
  Contains data like base and limit registers, page tables, or segment tables that define the memory allocated to the process.

- **Accounting Information**:  
  Tracks metrics like CPU usage, time limits, job or process numbers, and resource usage.

- **I/O Status Information**:  
  Contains a list of I/O devices allocated to the process and open file descriptors.

> The OS uses the PCB during context switching to save and restore process states and ensure proper execution control.
