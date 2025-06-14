
## System Calls - Divided into Five Major Categories

An essential function of the operating system is to provide **system calls** that allow programs to interact with hardware and various OS services.

System calls are generally divided into five major categories:

### 1. Process Control

This category includes system calls used for **managing and controlling processes**.

![Process Control System Calls](attachments/Pasted%20image%2020250610071119.png)

**Key operations include:**

- Creating a new process
- Terminating a process (either normally or abnormally)
- Loading a program into memory
- Waiting for a child process to finish
- Suspending or resuming a process

**Process Termination:**

- A process may end **normally** (e.g., after completing its task)  
- Or it may terminate **abnormally** (e.g., due to an error)

> **Abort**: This is a system call used to **forcefully terminate a process** when it encounters a serious error or cannot continue execution.


## 2- File Manipulation ( File Managment )
![](attachments/Pasted%20image%2020250611191409.png)


## 3- Device Manipulation (Device Management)
![Device Management Diagram](attachments/Pasted%20image%2020250611191807.png)

- **I/O Devices** or any other peripheral devices.
- **Logically Attaching**: This doesn't refer to physically plugging in the device.  
  It means the device has been *logically recognized* by the operating system and is ready for use.  
  **Example**: Plugging in a USB flash drive — the OS detects and mounts it.  
## 4- Information Maintenanceپ

![](attachments/Pasted%20image%2020250611192140.png)

- These are system calls used to **maintain and retrieve important information** about the system or user.
- The OS uses them to track things like time, process IDs, and user info.

### 🛠️ Examples:
- `getpid()` → returns the **process ID** of the current process  
- `getuid()` → returns the **user ID**  
- `time()` → returns the **current system time**  
- `uname()` → returns general **system information** (like OS name)

> In short:  
> **Information Maintenance** system calls are used to retrieve or manage vital information about the system or the user.


## 5- Communications
![Process Communication](attachments/Pasted%20image%2020250611192357.png)

- Processes often need to **communicate with each other** to exchange data or coordinate actions.
- This is known as **Inter-Process Communication (IPC)**.
- Communication can happen in two ways:
  - **Direct Communication**: One process sends a message directly to another.
  - **Indirect Communication**: Messages are passed via an intermediary like a **mailbox**, **pipe**, or **message queue**.

###  Common System Calls:
- `pipe()` → creates a unidirectional communication channel  
- `msgget()`, `msgsnd()`, `msgrcv()` → message queue functions  
- `shmget()` → used for **shared memory** communication  
- `socket()` → used in **network communication** between processes (often across systems)

> In short:  
> **Communication system calls** enable processes to send and receive information, either directly or through an intermediate mechanism.
