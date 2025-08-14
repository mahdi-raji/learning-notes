# Scheduling Criteria

**On what basis are we going to compare them or decide the efficiency of a scheduling algorithm?**

## CPU Utilization
We want to keep CPU as busy as possible, ranging from 0 to 100 percent.  
- **Ideal range:**  
  - 40% → lightly loaded system  
  - 90% → heavily loaded system  

## Throughput
The number of processes that are completed per time unit.  

## Turnaround Time
We are seeing this from the point of view of a process.  
- Measured from **start to end** of the process.  
![Turnaround Time](attachments/Pasted%20image%2020250814114108.png)  

## Waiting Time
The sum of periods a process spends **waiting in the ready queue**.  
- When we talk about scheduling, it means the **scheduler is assigning CPU to different processes**.  
- Once the CPU gets a process, the **time it executes in CPU doesn't depend upon the scheduler**.  
- **Waiting time** is the time that it takes for the scheduler to give the process to CPU.  

## Response Time
- Turnaround time is the time that a process takes to complete from start to end.  
- **Response time** is the time from start to **first response**, not the output.  
- Example:  
  - Let's say we have a video file. We double click on it. The video takes a little time to load for us to see output.  
  - **Turnaround time:** total time from click to finish ( see the video ).  
  - **Response time:** time until the process first starts executing in background.  

![Response Time](attachments/Pasted%20image%2020250814120022.png)  
