# OOP Principles
### Inheritance : create new classes that reuse, extend, and modify the behavior defined in other classes.primary characteristics of object-oriented programming
#### base class: The class whose members are inherited
#### derived class: class that inherits those members, can have only one direct base class.

### Abstract base classes:  prevent direct instantiation,used only if a new class is derived from it

### Abstract and virtual methods: Virtual methods have an implementation and provide the derived classes with the option of overriding it. Abstract methods do not provide an implementation and force the derived classes to override the method. so, abstract methods have no actual code in them, and subclasses HAVE TO override the method.

### virtual: keyword modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class

resource: https://stackoverflow.com/questions/14728761/difference-between-virtual-and-abstract-methods#:~:text=Virtual%20methods%20have%20an%20implementation,HAVE%20TO%20override%20the%20method.

```
public abstract class E
{
    public abstract void AbstractMethod(int i);

    public virtual void VirtualMethod(int i)
    {
        // Default implementation which can be overridden by subclasses.
    }
}

public class D : E
{
    public override void AbstractMethod(int i)
    {
        // You HAVE to override this method
    }
    public override void VirtualMethod(int i)
    {
        // You are allowed to override this method.
    }
}
```

#### Interfaces blueprint of a class, all the methods which are declared inside the interface are abstract methods. It cannot have method body and cannot be instantiated,methods are public and abstract by default. 

resource: https://www.javatpoint.com/c-sharp-interface#:~:text=Interface%20in%20C%23%20is%20a,t%20be%20achieved%20by

#### Sealed Class: A class that  prevent other classes from inheriting from it, or from any of its members.

#### Derived class hiding of base class members 
##### new keyword explicitly hides a member that is inherited from a base class

### Polymorphism: many forms, the ability of objects of different types to provide a unique interface for different implementations of methods.

Types of Polymorphism:

* Static or compile-time polymorphism (for example, method overloading and operator overloading).

* Dynamic or runtime polymorphism (for example, overriding).

### Object-Oriented programming:  creating objects that contain both data and methods.

- OOP is faster and easier to execute

- OOP provides a clear structure for the programs

- OOP helps to keep the C# code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug

- OOP makes it possible to create full reusable applications with less code and shorter development time

resource: https://www.w3schools.com/cs/cs_oop.php