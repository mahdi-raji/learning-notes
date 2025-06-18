![](attachments/Pasted%20image%2020250618233206.png)
- where there is shared memory?
	in the address space of the process creat the shared memory segment.
- Process a will create the shared memory region and it will lay in the address of process a . 
- process b will attach the region of shared memory that was created by process a to its own address.
-  in the shared memory, prventation of accessing by another process's memory  restriction is removed.
- os doesn't interfere in creating of shared memory.

## Producer Consumer Problem
for example a compiler may produce assembly code wich is consudmey bthe assembler and they have to work concurrently.

- one solution is using shared memory.
- we must have a buffer of items that can be filled by the producer and emptied by the consumer.
- the buffer will reside in a region of memory that is shared by the producer and consumer processes.
- **what is exactly buffer and where does it place ???**
- ![](attachments/Pasted%20image%2020250618234005.png)
![](attachments/Pasted%20image%2020250618234233.png)
