## Process States in an Operating System

As a **process executes**, it goes through different **states**.  
These states describe **what the process is currently doing** (its current activity).

> 🧠 The state of a process is a key part of how the OS manages and schedules processes.

---

### 📋 Common Process States

| State          | Description                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------- |
| **NEW**        | The process is being created.                                                                              |
| **READY**      | The process has been created and is ready to be assigned to a processor. It is waiting in the ready queue. |
| **RUNNING**    | The process is currently being executed on the CPU. Instructions are actively running.                     |
| **WAITING**    | The process is waiting for some **event to occur**, such as an I/O completion or a signal.                 |
| **TERMINATED** | The process has **finished** execution.                                                                    |

> 📌 A process can transition between these states depending on scheduling, I/O operations, or completion of execution.

---

### 🔁 Process State Transition Diagram

The diagram below shows how a process can move between states:

![Process State Diagram](attachments/Pasted%20image%2020250615195340.png)

---

