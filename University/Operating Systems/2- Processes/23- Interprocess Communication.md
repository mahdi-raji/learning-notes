there are different processes in our system and they may need to communicate to each other 
( IPC = Interprocess Communication )

![](attachments/Pasted%20image%2020250618225857.png)
mostly in cooperating proceess we will need interporcess communication.

## Why we need cooperation: 

- Information Sharing:
	when several users are intersted in a single media.

- Computation speed up: 
	we can split a task to multiple tasks and run them concurently. since all of these is for one task they will need to communicate with each other.

- Modularity:
	deviding system to seperate modules. they will need to cooperate with each other.

- Convenience:
	a user maybe listen to music and using word they are differenet processes but they an cooprate with each other convinently.



## How does interprocess communication actully takes place?

![](attachments/Pasted%20image%2020250618231530.png)
Shared memory: we stablish a region of memory that will be shared by the 
cooperating processes. 
Messag passing: Message are exchanged between the cooperating processes
![](attachments/Pasted%20image%2020250618231613.png)
in a (shared memory)=> process a write and process be read it.
in b (message passing)=> a will create the message and kernel will get the message and then kernel will understand that the message is for process b and then it will send it to process b.