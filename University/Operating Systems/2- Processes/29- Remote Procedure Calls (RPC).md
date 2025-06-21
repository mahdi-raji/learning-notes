RPC come to play when the processes connected to diffrenet networks to communicate.

![](attachments/Pasted%20image%2020250619182742.png)
in ipc the message sent to kernel are just packets of the data but in rpc its not only happening in one system and it has to travel to other system so these messages are well structured.
- **Daemon** is a background program or process that runs on a system without direct user interaction.  
	It usually runs continuously or starts when needed to perform specific system or network tasks.
	Examples include:
	- `httpd` (web server)
    
	- `sshd` (SSH server)
    
- A rendezvous daemon that manages client requests on a specific port.
    
![](attachments/Pasted%20image%2020250619183218.png)
- Each message is addressed to an port on the opther system.
With function we mean the service that is reside in another system and is called by another system remotly; so we need to call that function and pass our parameters.


- The client interacts with a predefined interface, which internally knows how to reach the server — including the port and communication details — so the client doesn’t need to worry about how the communication takes place.
 - **Parameter Marshaling:** means converting parameters into a network-friendly format — so they can travel across machines.
 - On the server side, a stub receives the request, unpacks the parameters, and calls the actual procedure on the server. It acts as a bridge between the network message and the real function logic.
- - A definition file (like `.proto`) specifies which methods the server has and how messages are structured.
    
- Tools like `protoc` take this definition and automatically generate client and server stubs.
    
- The client stub acts like a local function that packages requests and sends them to the server.
    
- The server stub receives requests and calls the actual server functions.
    
- The user or client programmer simply calls functions without needing to know the details of network communication.
