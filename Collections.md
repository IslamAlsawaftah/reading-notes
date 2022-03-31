### Collections  provide a more flexible way to work with groups of objects

A collection is a class, so you must declare an instance of the class before you can add elements to that collection.

generic collection enforces type safety

### Example 
List `<T>` class, which enables to work with a strongly typed list of objects.


### System.Collections.Generic Classes

* Dictionary<TKey,TValue> Represents a collection of key/value pairs that are organized based on the key.
* List `<T>` Represents a list of objects that can be accessed by index. Provides methods to search, sort, and modify lists.
* Queue `<T>` Represents a first in, first out (FIFO) collection of objects.
* SortedList <TKey,TValue> Represents a collection of key/value pairs that are sorted by key based on the associated IComparer<T> implementation.
* Stack `<T>` Represents a last in, first out (LIFO) collection of objects.


### System.Collections Classes

* ArrayList Represents an array of objects whose size is dynamically increased as required.
* Hashtable Represents a collection of key/value pairs that are organized based on the hash code of the key.
* Queue Represents a first in, first out (FIFO) collection of objects.
* Stack Represents a last in, first out (LIFO) collection of objects.

### Using LINQ to Access a Collection

can be used to access collections. LINQ queries provide filtering, ordering, and grouping capabilities.

### Iterators: An iterator is used to perform a custom iteration over a collection.

### Enumeration types: special "class" that represents a group of constants 

1- By default, the first item of an enum has the value 0

```
enum Months
{
  January,    // 0
  February,   // 1
  March,      // 2
  April,      // 3
  May,        // 4
  June,       // 5
  July        // 6
}
```

2- To create an enum, use the enum keyword , and separate the enum items with a comma

3- specify integral numeric type

4- access enum items with the dot

### Enumeration types as bit flags

define enum members, values of  enum members should be the powers of two.

### The System.Enum type and enum constraint

system.enum : used in a base class constraint to specify that a type parameter is an enumeration type.

struct constraint is used to specify that a type parameter is a non-nullable value type.

### Conversions

cast an enum value to its underlying type, the result is the associated integral value of an enum member.









