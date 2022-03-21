### Classes & Objects

class: is a reference type,blueprint variable contains the value null until create an instance of the class using new operator.
declare object : MyClass mc = new MyClass();
````
Customer object3 = new Customer();
Customer object4 = object3;
````

Any changes to the object made through object3 are reflected in subsequent uses of object4

Class inheritance: i can use another class behaviours and methods inside my class except the constructors. 
c# doesnt support multiple inheritance
```
public class Manager : Employee
{
    // Employee fields, properties, methods and events are inherited
    // New Manager fields, properties, methods and events go here...
}
```
abstract: An abstract class contains abstract methods that have a signature definition but no implementation.
i can't make object from it,showing only essential information to the user,To achieve security hide certain details 
To access the abstract class, it must be inherited from another class,to use abstract class we inherit it 

```
abstract class Animal
class Pig : Animal

An interface is a completely "abstract class"
interface IAnimal 
class Pig : IAnimal
```

Seald class No class can be derived from a sealed class,  restrict the users from inheriting the class
Sealed method: method cannot be overridden

complete reads about contructor https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors
```
public class Person
{   // Constructor: factory for building object, method whose name is the same as class name, set default values
    // Constructor that takes no arguments:parameterless constructor.
    public Person() 
    {
        Name = "unknown";
    }

    // Constructor that takes one argument:
    public Person(string name)
    {
        Name = name;
    }

    // Auto-implemented readonly property:
    public string Name { get; }

    // Method that overrides the base class (System.Object) implementation.
    public override string ToString()
    {
        return Name;
    }
}
```

Static Constructors: initialize any static data, perform a particular action that needs to be performed only once.
Remarks:https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/static-constructors

Private Constructors: used in classes that contain static members only, class has one or more private constructors and no public constructors, cannot create instances of this class.

Instance constructors: to specify the code that is executed when you create a new instance of a type with the new expression.you can call a constructor of a base class.
example: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/instance-constructors

Properties : enable a class to expose a public way of getting and setting values, access private field
A get property accessor is used to return the property value, and a set property accessor is used to assign a new value. 

```
class Person
{
  private string name; // field
  public string Name   // property
  {
    get { return name; }
    set { name = value; }
  }
}

```
```

class Program
{
  static void Main(string[] args)
  {
    Person myObj = new Person();
    myObj.Name = "Liam";
    Console.WriteLine(myObj.Name);
  }
}
```
Automatic Properties:  short-hand 
```
class Person
{
  public string Name  // property
  { get; set; }
}
```

```
class Program
{
  static void Main(string[] args)
  {
    Person myObj = new Person();
    myObj.Name = "Liam";
    Console.WriteLine(myObj.Name);
  }
}
```

Encapsulation, is to make sure that "sensitive" data is hidden from users:
1- declare fields/variables as private
2- provide public get and set methods

Stack and Heap:
stack and heap help us run our code, 
heap:  hold information, we can grab what we need quickly. 
stack: keep track of what's going on in our application, we have to take off the top one to get to the one underneath it.

pointer: is a reference,is a chunk of space in memory that points to another space in memory. 

The garbage collector: manages the allocation and release of memory. The garbage collector serves as an automatic memory manager.
When objects are no longer used then it will reclaim those objects by clearing their memory, and keeps the memory available for future allocations.

reference:https://www.tutorialspoint.com/What-is-garbage-collection-in-Chash#:~:text=The%20garbage%20collector%20(GC)%20manages,objects%20that%20use%20that%20memory.
