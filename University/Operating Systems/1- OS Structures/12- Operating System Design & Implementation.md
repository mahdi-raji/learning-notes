# Operating System Goals
![OS Goals](attachments/Pasted%20image%2020250614105347.png)

It's not easy to define and specify the exact goal of an operating system — it depends on both **user requirements** and **system requirements**.

## User Goals

The OS should provide an environment that is:

- **Convenient to use**
- **Reliable**
- **Safe and fast**
- **Easy to learn and operate**

## System Goals

From the system perspective, the OS should be:

- **Easy to design, maintain, implement, and operate**
- **Flexible**
- **Reliable**
- **Error-free**
- **Efficient**

> There are no strict rules to follow in order to achieve these goals.  
> However, there are some fundamental **principles** that guide OS design and development.
## Mechanisms and Policies

- **Mechanism**: Determines *how* to do something.  
- **Policy**: Determines *what* will be done.

### Real-Life Analogy

For driving a car:

- The **mechanisms** are the internal components (engine, transmission, etc.) that enable the car to move.
- The **policy** is a rule — for example, *"Do not exceed 50 km/h on this road."*

> One important principle in system design is the **separation of policy from mechanism**.

### Why is Separation Important?

The **car's mechanism** should not be tied to the **route's policy**.  
If the car is *mechanically limited* to 50 km/h and the road policy changes to 40 km/h, the car will require modifications — this reduces **flexibility** and increases **maintenance**.

### OS Example: Resource Allocation

When a process requests a resource:

- The **mechanism** defines *how* the resource will be allocated.
- The **policy** decides *whether* the resource should be allocated to that process or not.

After defining policies and mechanisms, we proceed to the **implementation phase**.

## Implementation

![](attachments/Pasted%20image%2020250614110712.png)  
![](attachments/Pasted%20image%2020250614110719.png)  
![](attachments/Pasted%20image%2020250614110742.png)
