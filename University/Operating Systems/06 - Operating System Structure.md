# Core Concepts of Operating Systems

## Fundamental Features

There are two common features that all operating systems should have:

1. **Multiprogramming**  
2. **Time Sharing**

---

## Multiprogramming

Multiprogramming is the **capability of running multiple programs** by the CPU.

![Multiprogramming Diagram](attachments/Pasted%20image%2020250605202031.png)

The main goal of multiprogramming is to **increase CPU utilization**.

- **Job:** A job is a unit of work that needs to be executed.
- **Memory Limitation:** We cannot load all the jobs into memory (RAM) at once.
- The operating system is responsible for **managing and assigning jobs** to the CPU for execution.

> **Problem in Simple Execution:**  
> If Job 1 starts execution, the CPU becomes fully occupied and **cannot run Job 2** at the same time.  
> However, if Job 1 needs to use another resource (e.g., I/O devices), the CPU becomes **idle**, which is inefficient.

In multiprogramming:

- When **Job 1** goes to use I/O devices,
- The **CPU is released** and can now be used by another job (e.g., Job 2),
- This prevents the CPU from remaining idle.

> **Real-Life Analogy:**  
> A lawyer doesn’t take care of only one client.  
> When one client’s case goes to trial (i.e., waiting on I/O),  
> the lawyer starts working on other clients’ cases too.

![CPU Idle vs Multiprogramming](attachments/Pasted%20image%2020250605202600.png)
# Time-Sharing (Multi-Tasking)

- ### Time-Sharing Concept
In time-sharing systems, the **CPU switches between jobs** frequently and quickly so that **multiple users can interact with the system simultaneously**.

![CPU switches between jobs](attachments/Pasted%20image%2020250605203221.png)

- ### Key Points:
- CPU switches between programs (jobs) so fast that users feel like their programs are running continuously.
- This **switching appears very frequently and quickly**, giving the illusion of direct and exclusive access.
- There is a **direct connection between the user and the system**, unlike batch systems.

![Users sharing the system](attachments/Pasted%20image%2020250605203243.png)

> The users don't realize that they are sharing the system.

- ## Human Speed vs CPU Speed
	Let's say **User1 is interacting** with the system.

- Since human interaction is **much slower than CPU speed**, during that time gap, the **CPU can serve User2** or others.
- This time-sharing among users is **handled by CPU scheduling algorithms**.

- ## Programs and Processes
- Each user has at least **one program loaded in memory** to be executed.
- When the program is being executed, it is called a **process**.

- ### Why Multi-Programming Does **NOT** Have Direct User Interaction

- Multi-Programming focuses on **maximizing CPU utilization** by keeping multiple programs in memory simultaneously.
    
- It is designed to **run multiple programs concurrently**, but **does not provide an interactive interface** for users.
    
- Programs are often executed in the background or batch mode, without user input during execution.
    
- Users submit jobs and wait for results later, so **there is no real-time, direct interaction** between user and system.

- ### Why Time-Sharing **HAS** Direct User Interaction

- Time-Sharing builds upon Multi-Programming by adding an **interactive interface** for users.
    
- CPU rapidly switches between multiple user processes, giving the illusion of exclusive access.
    
- Users can **input commands and get immediate responses** from the system.
    
- This **real-time interaction** enables multiple users to share the system concurrently while feeling like they have dedicated access.