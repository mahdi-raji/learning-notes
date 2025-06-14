	
# Categorization of Computer Systems Based on Number of General-Purpose Processors

## Single Processor

In a single processor system, there is only one **general-purpose processor** responsible for executing all instructions.
![](attachments/Pasted%20image%2020250603202858.png)
> **Note on Special-Purpose Processors:**  
> Special-purpose processors are designed for device-specific tasks. For example, a keyboard often includes a small microprocessor dedicated to converting key presses into binary signals specific to that device.  
>
> These special-purpose processors are **not counted** when categorizing a system as single or multiprocessor because the classification refers only to **general-purpose processors** that run the main program logic.


## Multiprocessor

A multiprocessor system contains **more than one general-purpose processor** working together.

![](attachments/Pasted%20image%2020250603204343.png)

- **Throughput:** The total amount of data that can be processed or transferred within a given time increases because multiple processors work simultaneously.  
- **Economy of Scale:** Multiprocessor systems are more economical as multiple processors share the system resources, improving efficiency and reducing overall cost per processing unit.  
- **Increased Reliability:** With multiple processors, if one processor fails, others can continue functioning, providing backup and improving the system's fault tolerance.
### Types Of Multiprocessor Systems:
![](attachments/Pasted%20image%2020250603204612.png)
- ## Symmetric Multiprocessing (SMP)**

In Symmetric Multiprocessing, **all processors are equal** and share the same memory and I/O resources. Each processor runs an identical copy of the operating system, and tasks can be scheduled on any processor. This setup allows for:

- **Load balancing:** The system can distribute tasks evenly among processors.  
- **Improved performance:** Multiple processors work in parallel, speeding up processing.  
- **Simplified programming model:** Since all processors are identical, the OS handles them uniformly.

- ## Asymmetric Multiprocessing (AMP)

In Asymmetric Multiprocessing, processors are **not equal** and have designated roles. One processor (the master) controls the system and manages tasks, while other processors (slaves) execute assigned tasks under the master’s control. Characteristics include:

- **Master processor** handles OS, I/O, and task scheduling.  
- **Slave processors** perform specific computations or tasks as directed.  
- Often used in systems where tasks are well-defined and divided.  
- Can simplify some aspects of design but may limit flexibility and scalability compared to SMP.


## Clustered  

![](attachments/Pasted%20image%2020250603211348.png)
