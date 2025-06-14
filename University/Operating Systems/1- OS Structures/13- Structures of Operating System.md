## Simple Structure

![Simple Structure](attachments/Pasted%20image%2020250614111638.png)

### Example: MS-DOS

MS-DOS is a classic example of a **simple operating system structure**.

### Layer Access Overview

- At the bottom: **ROM BIOS device drivers** (base hardware)
- **Device drivers** can access the BIOS
- **Resident system programs** can access both device drivers and BIOS
- **Application programs** can access resident system programs and device drivers

> BIOS device drivers and hardware are essentially accessible from all higher levels.

### Problem with This Structure

- Such **freedom of access** makes the system vulnerable.
- **Errant or malicious programs** can directly interact with hardware or critical drivers.
- This can lead to the **entire system crashing** — making it **not well-structured** or **well-designed**.

> ⚠️ However, this was not a fault of the OS designers.  
> The **Intel 8088** CPU (used in early PCs) lacked support for:
> - Dual-mode operation (user vs kernel mode)
> - Hardware-based memory protection

## Monolithic Structure

![Monolithic Structure](attachments/Pasted%20image%2020250614112615.png)

This structure was used in **early UNIX operating systems**.

In a monolithic structure, the **entire operating system** — including all core functionalities such as:

- **File system management**
- **Process scheduling**
- **Signal handling**
- **Memory management**
- **Device I/O**

...is implemented in **a single, large kernel**.

### Limitations

- All services run in the **same address space**, and there’s **no modular separation**.
- Because everything is tightly packed in one layer, **implementation, maintenance, and debugging** become **very difficult**.
- Even a small change can affect the whole system, increasing the risk of introducing bugs.

> ⚠️ While monolithic kernels can be fast due to direct function calls within the kernel, they suffer from **poor modularity** and are **hard to extend or maintain**.
## Layered Structure

![](attachments/Pasted%20image%2020250614122517.png)

In a layered structure, the operating system is divided into different levels or layers.

- This approach makes the system **easier to implement and debug**.
    
- It also helps to **protect the hardware** from direct access by higher levels.
    
- Designing the layers is **complex**. You have to carefully decide which layer should be below or above another.  
    For example:
    
    - The layer handling the **backing store** (like cleaning virtual memory algorithms) must be **below** the layer responsible for **memory management** because memory management depends on backing store services.
        
- It can be **less efficient** than other architectures.
    
    - If one layer needs a service from a lower layer, the request must go **step-by-step through each intermediate layer**, which may slow down the system.


## Microkernel:
![](attachments/Pasted%20image%2020250614134022.png)
In the **microkernel** approach, the core of the operating system kernel is kept minimal and is implemented as the **microkernel** itself.  
Other functionalities and services are implemented as **user-level system programs** outside the microkernel.

- The main role of the microkernel is to provide **communication** between the client programs and these user-level services.
    
- When a client program makes a request, the microkernel facilitates the communication using **message passing** to the appropriate service that will handle the request.
    

This design promotes better **modularity** and **reliability** since services run independently at the user level, reducing the risk of system-wide crashes.

Since most of the functionalities are implemented in **user mode** (outside the kernel), if one of these services crashes, **it usually does not cause the entire system to crash**. This improves system **stability** and **reliability**.

However, this design comes with a trade-off:  
**Performance may decrease** because communication between the client program and services relies heavily on **message passing**, which is slower than direct procedure calls within a monolithic kernel.


## Modules

![](attachments/Pasted%20image%2020250614135125.png)

The **Modules** approach is considered one of the best current methodologies for OS design and often involves **object-oriented programming (OOP)** principles.

- The **core kernel** contains only the essential functionalities.
    
- Other functionalities are implemented as **modules** that can be loaded into the kernel either at **boot time** or **runtime**.
    

Similar to the layered system, each kernel section has **defined and protected interfaces**, but modules offer more **flexibility**:

- Any module can **call other modules directly** without having to pass through all intermediate layers, which improves efficiency.
    
- Unlike the microkernel approach, **modules do not require message passing** for communication, leading to better performance.