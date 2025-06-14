## Operating System Generation
 ![](attachments/Pasted%20image%2020250614153039.png)

## System Boot

![Boot Process Diagram](attachments/Pasted%20image%2020250614153405.png)

**Boot**: The procedure of starting a computer by loading the kernel into memory.

But hardware doesn’t inherently know how to load the kernel. So how does system booting take place?

### Bootstrap Program

A **bootstrap program** is a small piece of code stored in **Read-Only Memory (ROM)** that locates and loads the operating system kernel into memory.

> It is the very first code executed when the system is powered on.

- **Why can't the bootstrap program be infected by a computer virus?**  
  A computer virus attempts to **modify or manipulate** code. Since ROM is **read-only**, it **cannot be altered**, which protects the bootstrap program from infection.

---

### Firmware

Firmware is also stored in ROM. On small embedded devices (e.g., routers, microwaves):

- Both the **bootstrap program** and the **operating system** may reside entirely in ROM.
- To update or change anything in ROM, traditionally you had to **replace the physical chip**.

> This problem was solved by **EPROM (Erasable Programmable ROM)** and later **Flash memory**, which allows reprogramming.

---

### System is Running

![System Running State](attachments/Pasted%20image%2020250614154030.png)
