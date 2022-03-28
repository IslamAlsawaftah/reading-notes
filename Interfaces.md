# Interfaces: blueprint of a class. It is like abstract class because all the methods which are declared inside the interface are abstract methods.

resource: https://www.javatpoint.com/c-sharp-interface#:~:text=Interface%20in%20C%23%20is%20a,t%20be%20achieved%20by%20class.

### used to achieve multiple inheritance, and fully abstraction

### Notes about Interface

* can't be instantiated directly,cannot contain a constructor,A class or struct can implement multiple interfaces. A class can inherit a base class and also implement one or more interfaces.

* Interface metods public and abstract by default.

* Interfaces can contain properties and methods, but not fields.

* To implement an interface, use the : symbol

* To implement multiple interfaces, separate them with a comma

* can’t have private members.

* defined with the keyword ‘interface‘.

* We can use the reference variable of an interface. For example

```
using System
namespace CsharpInterface {

  interface IPolygon {
    // method without body
    void calculateArea(int l, int b);

  }

  class Rectangle : IPolygon {

    // implementation of methods inside interface
    public void calculateArea(int l, int b) {

      int area = l * b;
      Console.WriteLine("Area of Rectangle: " + area);
    }
  }

  class Program {
    static void Main (string [] args) {
       
      // using reference variable of interface
      IPolygon r1 = new Rectangle();
    
      r1.calculateArea(100, 200);
    }
  }
}
``` 

### Why And When To Use Interfaces

1) To achieve security - hide certain details and only show the important details of an object (interface).

2) C# does not support "multiple inheritance" (a class can only inherit from one base class). However, it can be achieved with interfaces, because the class can implement multiple interfaces.

resource: https://www.w3schools.com/cs/cs_interface.php

### Syntax for Interface Declaration

```
interface  <interface_name >
{
    // declare Events
    // declare indexers
    // declare methods 
    // declare properties
}
```

### Syntax for Implementing Interface

```
class class_name : interface_name
```
resource: https://www.geeksforgeeks.org/c-sharp-interface/

### Unit Testing and Interface

```
public interface IFeedable
{
   string Eat()
   {
      return "the feedable is eating";
   }
}

public class HouseCat : IFeedable
{
   public string Name { get; set; }
   public HouseCat(string name)
   {
      Name = name;
   }
}
```

Based on the class above and the interface it implements, we should expect that a call to .Eat() on an instance of a HouseCat will return the default implementation.

```
[TestClass]
public class CatTests
{
   [TestMethod]
   public void TestHouseCatImplementsEatMethod()
   {
      IFeedable test_cat = new HouseCat("test");
      Assert.AreEqual("the feedable is eating", test_cat.Eat());
      // This test passes. Don't believe us? Try it yourself!
   }
}
```

In this situation, we test the contract that the interface is supposed to be upholding, but not the interface itself.

resource: https://education.launchcode.org/csharp-web-development/chapters/interfaces-and-polymorphism/testing-interfaces.html


