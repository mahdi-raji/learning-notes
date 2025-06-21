## Issues:
![](attachments/Pasted%20image%2020250621202134.png)

![](attachments/Pasted%20image%2020250621203531.png)
- client sends a request to the server and server processes it after processing the server most send and acknowledgment back to the client to say that request has been fulfield. the client send requests untill the server send back an aknowledgment.
### Problem:

In network communications like RPC,

- The client needs to know **which port on the server** to connect to in order to call a specific procedure or service.
    
- But in high-level protocols like RPC, ports are often not hardcoded or the server may change ports dynamically.
    

---

## First solution (simple and limited):

- The server pre-assigns specific ports (e.g., port 80 for web server).
    
- These ports are communicated to the client (e.g., via `.proto` files or configuration).
    
- The client directly connects to these ports.

**Problem:**

- Low flexibility (if the server changes port, clients must update)
    
- Poor scalability (limited number of services based on reserved ports)
## Second solution (Rendezvous mechanism / Matchmaker):

- A **central service or daemon** runs on a fixed port on the server (e.g., port 5000).
    
- When the client wants to call a procedure, it first sends the procedure name to this service.
    
- This service (called the **matchmaker** or **rendezvous daemon**) looks up which port or server handles that procedure.
    
- Then it returns the proper port to the client.
    
- The client then connects directly to that port to perform the RPC call.
    
## How RPC Works with Rendezvous (Step-by-Step)

![](attachments/Pasted%20image%2020250621204908.png)
1. The user (client) wants to use a service (Procedure X).  
2. The kernel sends a message to the matchmaker daemon's port to query the port number of Procedure X.  
3. The matchmaker receives the message and looks up the answer.  
4. The matchmaker replies to the client with the port number P.  
5. The kernel inserts port P into the client's RPC message.  

![](attachments/Pasted%20image%2020250621205131.png)
6. The kernel sends the RPC request with the parameters to Procedure X at port P. 
7. The daemon listening on port P receives the message, processes the request, and sends back the output.  
8. The kernel receives the reply and passes it to the user (client).