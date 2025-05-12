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
	- Reference type arrays are only mostly safe when storing values because ofarray covariance. I view array covariance as an early design mistake that’s beyond the scope of this book but example :
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
	

				 
