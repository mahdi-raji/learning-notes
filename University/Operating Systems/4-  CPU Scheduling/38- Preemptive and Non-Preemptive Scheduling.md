
- **CPU Scheduler:** the one who is going to select the ready process that will get cpu for it execution. 
- **Dispatcher:** the one who is going to give the cpu to the process selected by the scheduler.
	- **Duties:**
	- Perform a **Context Switch** (save the state of the current process and load the state of the new process)
	- Switch the CPU from **Kernel Mode** to **User Mode**
	- Jump to the starting address of the new process to resume or start its execution
	
	- **Important:** The dispatcher must be fast because the time taken between stopping one process and starting another is called **Dispatch Latency**, which is part of the system overhead.

## CPU Scheduling Happens in 4 circumstances:
![](attachments/Pasted%20image%2020250814112153.png)
Let’s say we have a shared memory and a preemptive scheduling system. Process 1 is writing to the shared memory when it gets preempted by the scheduler. Process 2 then starts running and attempts to write to that same shared memory. Since Process 1’s write operation was not completed, Process 2 may end up reading or writing inconsistent data.