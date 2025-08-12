
we only duplicate that thread or all the threads in a process? 
![](attachments/Pasted%20image%2020250812215835.png)

witch version of fork to use and when?
exec will replace all the **entire process** ( including all the threads )

if exec is called immediatly:
even if we duplicate all the process it is going to be useless.

if the separate process doesnt call exec() after forking:
then the seprate should process all the threads!


