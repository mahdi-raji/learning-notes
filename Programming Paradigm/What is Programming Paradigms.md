[What is Programming Paradigms](What%20is%20Programming%20Paradigms.md)
#programming #programming-paradigms 
## What is it actully?
Programming paradigms are different approaches or styles of writing programs that help you solve problems in specific ways.

A programming language may support one or multiple paradigms.  
For example, Python supports procedural, object-oriented, and functional paradigms.

Here are two simple examples to illustrate the idea:
```python
op = "sum"
a = 2
b = 3

if op == "sum":
	print(a + b)
elif op == "devide":
	print(a / b)
```

```Python
def calculate(a, b, op):
    if op == "sum":
        return a + b
    elif op == "divide":
        return a / b

op = "sum"
a = 2
b = 3
print(calculate(a, b, op))

```

At first you may be like, “oh, the first one is really hard to read and not as clear as the second one,” but what’s the actual difference?
_[It’s like trying to answer What came first, the chicken or the egg?](https://ui.dev/imperative-vs-declarative-programming)_
That’s it. 
**The first one** explicitly tells you **how** things are done — that’s called **Imperative**.
**The second one** focuses on **what** the result should be — that’s **Declarative**.
These two form the two main categories of programming paradigms, and each has many sub-paradigms.  
If I ever get enough free time and stop being this تنبل, you might actually find me exploring and learning many of them in my notes.

