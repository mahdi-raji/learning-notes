## Thread Cancellation

**Thread cancellation** is the act of terminating a thread before it has completed execution.

> **Example:** If multiple threads are concurrently searching for a value and one thread finds it, the other threads can be terminated.

**Target thread:** The thread that is to be canceled is often referred to as the *target thread*.

---

## Types of Thread Cancellation

![Thread Cancellation Types](attachments/Pasted%20image%2020250812222533.png)


In **deferred cancellation**, the target thread periodically checks whether it should terminate, allowing it to reach a safe point before exiting.


## Problems with Thread Cancellation

- Resources may have been allocated to a canceled thread.
- A thread may be canceled while data is being updated between threads, leading to inconsistent state.
- Often the OS will reclaim system resources, but in some cases, it may not be able to reclaim all of them.
- In deferred cancellation, one advantage is that the thread can check if it is safe to terminate before actually exiting.

---
