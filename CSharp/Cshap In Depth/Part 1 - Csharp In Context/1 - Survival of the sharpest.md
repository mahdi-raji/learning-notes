- statically typed language  
- compiler can help you avoid mistakes.  
- You can do that through documentation, but static typing lets you communicate in a machine-readable way.  
- Tuples :  
	- I advise that these be kept within the internal API of a program rather than  
		exposed publicly, because tuples represent a simple composition of values rather than  
		encapsulating them.
- Asynchrony has been difficult in mainstream languages for a long time. More niche
- But C# 5 brought a new level of clarity to programming asynchrony in a main-stream language with a feature usually referred to as async/await. The feature consistsof two complementary parts around async methods:
	- Async methods produce a result representing an asynchronous operation with noeffort on the part of the developer. This result type is usually Task.
	-  Async methods use await expressions to consume asynchronous operations. If the method tries to await an operation that hasn’t completed yet, the method pauses asynchronously until the operation completes and then continues.