![](attachments/Pasted%20image%2020250611193335.png)


 - In the lowest level we have computer hardware and top of that we have os and on top of that we have system programs and top ot that we have application programs.

![](attachments/Pasted%20image%2020250611193438.png)

![](attachments/Pasted%20image%2020250611193507.png)
![](attachments/Pasted%20image%2020250611193536.png)
![](attachments/Pasted%20image%2020250611193557.png)
- File modifcation and file management => Managment ( Outer ) and modify ( inner )

![](attachments/Pasted%20image%2020250611193705.png)
![](attachments/Pasted%20image%2020250611193807.png)
## Types of Loaders and Linkers

When a program is compiled, it generates an executable file that must be loaded into memory (RAM) before it can run. This task is handled by a **loader**, and depending on the system, various types of loaders and related tools may be used.

---

####  1. Absolute Loader

An **absolute loader** loads a program into a **fixed memory address** that is known in advance. If that address is already occupied, the program cannot be loaded.

- **Example:** Early computers in the 1960s.
- The program was manually written to run from a specific address, e.g., `1000h`.
- There is **no flexibility** in memory placement.

---

####  2. Relocating Loader

A **relocating loader** allows a program to be loaded into **any available memory location**. It adjusts the address references in the program during the loading process.

- **Example:** Modern operating systems like Windows or Linux.
- Programs are compiled with **relative addresses**, and the loader shifts them based on where the program is loaded in memory.
- Useful for **multitasking** environments.

---

####  3. Linkage Editor (Linker)

A **linker** connects multiple object files and creates a single executable file **before runtime**. This is done offline, during compilation.

- **Example:** When using GCC:
  ```bash
  gcc main.c math.c -o calc.exe
```
- Here, `main.c` and `math.c` are compiled and linked together into `calc.exe`.
    
- The final executable is ready to be loaded and run.
####  4. Overlay Loader

An **overlay loader** is used when the available memory is too small for the entire program. The program is split into parts (called **overlays**), and only the necessary part is loaded at any time.

- **Example:** Old game consoles like NES or Atari.
    
- Each game level is stored as a separate overlay.
    
- When the level changes, the loader replaces the old part in memory with the new one.
    
- Still used today in **embedded systems** with limited RAM.


![](attachments/Pasted%20image%2020250611193921.png)

- Some Prorgarms might be provided along the operating system but the its important to know that **they are not system porgrams** but they are application programs.
![](attachments/Pasted%20image%2020250611194614.png)