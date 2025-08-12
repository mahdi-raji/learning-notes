**Generics**

- their primary use was for collections
 - in .net1 it was 3 kinds of collections :
	- Array => Normal Array 
	- Object-based collections => 
			 - From system.object 
			 - no collection specific and not type safe			 
			 - They called array list but implementation looks like hashtable
	- Specialized collections =>
			 - Type Safe ArrayList
			 - StringCollection	
	- Arrays and Specialized collections are statically typed .
	- Reference type arrays are only mostly safe when storing values because of array covariance. I view array covariance as an early design mistake that’s beyond the scope of this book but example :
	```csharp
	string[] strings = new string[] { "hello", "world" }; 
	object[] objects = strings; 
	objects[0] = 42;
	```
	- The problem with array was we most specify the array size in creation of array 
	```csharp
	string[] names = new string[3]; // Fixed size
	names[0] = "Alice";
	names[1] = "Bob";
	// names[3] = "Charlie"; // Error: Array too small
	```
	
	- The problem with ArrayList was the problem with no type safe
	```csharp
	ArrayList list = new ArrayList();
	list.Add("Alice");
	list.Add(42); // No error, but causes problems
	string name = (string)list[1]; // Runtime error!
	```
	
	- The problem with StringCollection was that it only supported one type 
	```csharp
	StringCollection names = new StringCollection();
	names.Add("Alice");
	// names.Add(42); // Error: Only strings allowed
	// No IntCollection exists for integers!
	```
- **Generics** solve all of these problems.
```C#
static List<string> GenerateNames()
{
	List<string> names = new List<string>();
	names.Add("Gamma");
	names.Add("Vlissides");
	names.Add("Johnson");
	names.Add("Helm");
	return names;
}
static void PrintNames(List<string> names)
{
	foreach (string name in names)
	{
	Console.WriteLine(name);
	}
}
```
- You don't need to know the size of the collection
- The exposed api always used T everywhere it needs to be used and it improves the consistency and being error prone in compile time.
- It can be used by any elemnt types (string, int, class, and etc)
- Solves the problem of expressing an elemnt type as an input to a method ( Multiple Methods for Generting names sepcificly for the type )
- Methods can be generic too ( useful for when we want to be staticly typed in our method ).
- One of it powers is that it can be used to express a relationship between the types of regular parameters and the retrun types
```C#
- public T Echo<T>(T value) {
    return value;
}
```
- Generic Classes can pass theire type parameter to interfaces.
	- It will make the implementation of interfaces generic, responsive and type safe. ( forexample in List T  is inheratied from IEnumerable T )
- Generics Arity: number of type parameters of a deceleration.
- - Generics allow same name for multiple types as long as their kind or arity is different
```csharp
public enum IAmConfusing {}
public class IAmConfusing<T> {}
public struct IAmConfusing<T1, T2> {}
public delegate void IAmConfusing<T1, T2, T3> {}
public interface IAmConfusing<T1, T2, T3, T4> {}
```
	- ✅ Valid, but ❌ confusing — not recommended
-  It's common to have a non-generic static class as a helper for related generic types
```C#

public static class Tuple {
    public static Tuple<T1, T2> Create<T1, T2>(T1 a, T2 b) => new Tuple<T1, T2>(a, b);
}
```
- You can overload generic methods by number of type parameters 
- Type parameters in the same declaration must have unique names
- It's fine to use the same type as both generic arguments 
### What Can Be Generic in CSharp #

- **Types that can be generic:**
  - Classes
  - Structs
  - Interfaces
  - Delegates

- **Types that cannot be generic:**
  - Enums

- **Members that can be generic:**
  - Methods
  - Nested types

- **Members that cannot be generic:**
  - Fields
  - Properties
  - Indexers
  - Constructors
  - Events
  - Finalizers (destructors)

---

### Why a Field Using a Generic Type Is Not Generic Itself

```C#
public class ValidatingList<TItem>
{
    private readonly List<TItem> items = new List<TItem>();
}

```

- `ValidatingList<TItem>` is a generic class because it declares the type parameter `TItem`.
- The field `items` uses the generic type `List<TItem>`, but **it does not declare any new type parameters itself**.
- Therefore, `items` is **not a generic field**, it is just a field of a generic type.

---

### Generic Constructors Are Not Allowed
```C#
public class MyClass
{
    public MyClass<T>(T value) // ❌ Compile error: constructors cannot be generic
    {
    }
}
```
- C# does **not** allow defining generic constructors.

---

### Using Generic Static Methods Instead of Generic Constructors
```C#
public class MyClass
{
    public string Value;

    private MyClass(string value)
    {
        Value = value;
    }

    public static MyClass Create<T>(T input)
    {
        return new MyClass(input.ToString());
    }
}
```

```C#
var obj1 = MyClass.Create(123);            // T inferred as int
var obj2 = MyClass.Create("Hello");        // T inferred as string
var obj3 = MyClass.Create(DateTime.Now);   // T inferred as DateTime

```
- Instead of a generic constructor, define a generic static method.
- The generic method `Create<T>` can accept any type parameter.
- This approach works around the limitation and allows generic behavior.
- This allows you to **omit the explicit type** and still call the method correctly.

## Type Constraint
- `where T : IFormattable` ensures that `T` has a `ToString(string, IFormatProvider)` method.
    
- Without it, the compiler only sees `object.ToString()`, which doesn’t accept formatting arguments.
    
- C# supports several constraints: `class`, `struct`, `new()`, interfaces, base classes, or even other type parameters.
    
- Combining constraints allows powerful generic APIs (e.g., only allow types that are comparable and have a parameterless constructor).
    

- `: new()` type constraint specifies that a type argument in a generic class or method declaration must have a public parameterless constructor
	usage:
	```C#
	public class GenericRepository<T> where T : class, new()
	{
	    public T CreateEmpty()
	    {
        return new T();
	    }
	}
	```
	This is essential when your generic code needs to rely on specific behaviors from the type argument.