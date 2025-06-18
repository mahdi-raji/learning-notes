## Sysnc or async communication ( Synchronication issue ): 

![](attachments/Pasted%20image%2020250619010028.png)
when process is sending or receiving messsage, it can be blocking or nonblocking type.
- Blocking Send: sending process is blocked untill it received ( by mail box or process ).
- Nonblocking send: after sending message sending process resumes operation.
- Blocking Receive: The receiver blocks until a message is available.
- Nonblocking Receive: The reciever retreives either a vlaid message or a null.
## Buffering:
- messaged exchanged by communication processes reside in a temp queue, known as Buffer.
### Implementations of buffering:
#### Zero Capacity:
- Queue has max lengh of zero; thus its blocking and it only accepts one message at a time.( sender must block untill the recipient receives the message )
- so why we call it buffer? it acts like a link !
####  Bounded Capacity:
- finite length n. if queue is not full when a new message is net ints palce in the queue . if the link is full the sender must be blocked untill it gets free.
#### Unbounded Capacity:
- The queues length is inifinite. Sender never blocks!
