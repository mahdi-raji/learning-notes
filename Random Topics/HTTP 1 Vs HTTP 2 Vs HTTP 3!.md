https://www.youtube.com/watch?v=UMwQjFzTQXw

- http (Hyper text transform protocols ) is how browsers talks to webservers.
- at first http was for hyper text documents.
First was HTTP 0.9 =>
		Only HTML Files and GET HTTP Method and no http headers or status codes.
HTTP 1.0 => in 1996 Added status codes, headers and POST Http method.
	Each Request needed its own connection.
	
<img src="attachments/Pasted%20image%2020250622213155.png" width="300px">
with http1 every resource needed to tcp handshake and tls check and key exchange before the actual file.
=> in 1997 HTTP 1.1 comes out :
	Persistant Http Connections:
		the connection stays open until both of them are closed.
	Piplining:
		Sending multiple requests over one tcp connection.
	Chunk Tranfer Encoding:
		Server send responses in smaller chunks. 
	Better Caching.
the big problem:
	Blocking! if first request is in wait all other requests have to wait too.
Domain Sharding: 
	websites would save static assets on subdomains.
=> in 2015 HTTP 2 Arrived!
	Binary Framing Layer :
		Messages are devided into smaller units called frames.these are send over tcp connection. the binary frame layer handles all this.
		![](attachments/Pasted%20image%2020250624000215.png)
	Server push:
		a server can send extra resources
		![](attachments/Pasted%20image%2020250624000447.png)
	HPACK Compression ( Header Compression ):
		![](attachments/Pasted%20image%2020250624000527.png)
	 http 2 nature was handling packet loss 
2022 HTTP 3=> Quic !
	Instead of tcp Using UDP doesn't needs to setup a connection before sending the data. 
	
	