# CS4330FinalProject

# Language Purpose
## C#
Created in 2000, C# was originally intended as a “simple, modern, general purpose object-oriented language.” C# was Microsoft’s response to the release of Java, and originally looked very similar to Java. It was heavily object-oriented, until the 2.0 version’s release in 2005, which expanded the features to include generics, anonymous methods, and even different iterators, mirroring Java’s recent release of an enhanced for-loop in 2004. In 2007, C# established the LINQ (Language-integrated query), which provided a method to perform operations on collections of data in a much more logical way, and evolved the language in a completely divergent path compared to Java. In recent releases, the language has adapted to incorporate multiple paradigms, such as pattern-matching within the functional programming paradigm.
## Python
Originally developed around 1991 by Guido van Rossum, Python was intended to be simple and have high readability, as well as minimalism. It was heavily influenced by Lisp, as well as a language called ABC. The initial release contained exception handling, and was object-oriented primarily. 

# Unique Features
## C#
LINQ is a heavy unique feature that C# implemented initially. Interoperability of any language written in a .NET compliancy also enables it to access classes and libraries from code in other languages. The namespace feature of C# enables classes to be accessed independent of their directory. It uses Microsoft’s Dynamic-Link Library system to provide a single universal copy of a library, instead of necessitating multiple copies in every project directory. Another unique feature of C# is its operator overloading, which allows the developer to add additional functionality to basic operators in the language.

## Python
The importance of indentation and significant whitespace was unique to python, and assisted in enforcing readability in developers code. Python also includes Generator expressions, which are a different version of list expressions, and enable the run-time generation of iterable structures without consuming as much data.

# Name spaces
## C# 
Through the use of the “using” keyword in C#, external namespaces are allowed to be implemented and differentiated from local variables. 
```csharp
using System;

namespace SampleNamespace
{
    class SampleClass
    {
        public void SampleMethod()
        {
            System.Console.WriteLine(
              "SampleMethod inside SampleNamespace");
        }
    }
}
```

Namespaces can be nested as desired, to allow for proper closures, and it also enables a hierarchical system to be generated.

```c#

// Namespace Declaration
using System;

// The C# Station Namespace
namespace csharp_station 
{
    // Program start class
    class NamespaceCSS 
    {
        // Main begins program execution.
        public static void Main() 
        {
            // Write to console
            Console.WriteLine("This is the new C# Station Namespace."); 
        }
    }
}
```

## Python
Namespaces are implemented as dictionaries, or key-value pairs. The name is used as a key, and an object for the namespace is generated as a value. Every single module, class, function, etc. contains its own namespace, as well as a global namespace. This makes it easy to import other Python projects, even if there are identical names, as each name has an identifier for its scope, and imported modules contain the global namespace scope, which will not have a collision with any local variables.

```python
def scope_test():
    def do_local():
        spam = "local spam"

    def do_nonlocal():
        nonlocal spam
        spam = "nonlocal spam"

    def do_global():
        global spam
        spam = "global spam"

    spam = "test spam"
    do_local()
    print("After local assignment:", spam)
    do_nonlocal()
    print("After nonlocal assignment:", spam)
    do_global()
    print("After global assignment:", spam)

scope_test()
print("In global scope:", spam)
```

Output is:
```
After local assignment: test spam
After nonlocal assignment: nonlocal spam
After global assignment: nonlocal spam
In global scope: global spam
```


# Types

## C#
All basic types are supported, encompassing:

Alias |	.NET Type |	Type |	Size (bits) |	Range (values)
--- |   --- |  --- |    --- | ---
byte |	Byte	| Unsigned integer | 8 |	0 to 255
sbyte |	SByte |	Signed integer |	8 |	-128 to 127
int |	Int32 |	Signed integer |	32 |	-2,147,483,648 to 2,147,483,647
uint |	UInt32 |	Unsigned integer |	32 |	0 to 4294967295
short |	Int16 |	Signed integer |	16 |	-32,768 to 32,767
ushort |	UInt16 |	Unsigned integer |	16 |	0 to 65,535
long |	Int64 |	Signed integer |	64 |	-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807
ulong |	UInt64 |	Unsigned integer |	64 |	0 to 18,446,744,073,709,551,615
float |	Single |	Single-precision floating point type |	32 |	-3.402823e38 to 3.402823e38
double |	Double |	Double-precision floating point type |	64 |	-1.79769313486232e308 to 1.79769313486232e308
char |	Char |	A single Unicode character |	16 |	Unicode symbols used in text
bool |	Boolean |	Logical Boolean type |	8 |	True or False
object |	Object |	Base type of all other types		
string |	String |	A sequence of characters		
decimal |	Decimal |	Precise fractional or integral type that can represent decimal numbers with 29 significant digits |	128 |	(+ or -)1.0 x 10e-28 to 7.9 x 10e28
DateTime |	DateTime |	Represents date and time |	|	0:00:00am  1/1/01 to 11:59:59pm 12/31/9999

C# has value-types, and also classes represented under structs that operate just like value-types. Both are handled similarly, with allocation happening in memory at run-time.

Reference types are handled under the representation of actual classes, which contain references to variables that can be instantiated.

Structs also, essentially, allow for the creation of new value types.

## Python
Python doesn't necessarily have either value or reference types. The parameter passing method, and allowing for multiple returned results changes the scope of how Python handles variables. This boils down to Python's representation of mutable vs. immutable objects, since almost everything in Python is an object. This depends on the binding of the name to a value, and whether it is mutable or immutable. If the binding is mutable, then all names in the Python namespace will have the value changed when the mutable variable is changes. Otherwise, the variable cannot be changed.

Mutable objects are changed in functions as follows:
```python
def foo(bar):
    bar.append(42)
    print(bar)
    # >> [42]

answer_list = []
foo(answer_list)
print(answer_list)
# >> [42]
```
New value types can be created.


# Classes
## C#
Classes are defined in C# very similarly to java:
```c#
public class Customer
{
   // Fields, properties, methods and events go here...
}
```
New instances are created the same as well:
```c#
Customer object3 = new Customer();
Customer object4 = object3;
```
Constructors will be provided if one is not input in the object, initalizing variables by using values from the Default Values Table
Otherwise, they can be initialized in the same way as Java, or, if there is only one line of code within the constructor, they can be initialized in a simpler fashion:

```c#
public class Location
{
   private string locationName;
   
   public Location(string name) => locationName = name;

   public string Name
   {
      get => locationName;
      set => locationName = value;
   } 
}
```
When the reference is dereferenced, and set to be cleaned up by the Garbage Collection, **Finalizers** can be called on classes. They are declared as:

```c#
class Car
{
    ~Car()  // destructor
    {
        // cleanup statements...
    }
}
```

## Python

Classes in python are defined as following:

```python
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjectx.function()
```
Which would print:
```
This is a message inside the class.
```

This shows how MyClass is also instantiated, using a default constructor, and how the function is called on an object instance.

To create a constructor, or an initializer method, one may use the "__init__(self)" keyword, and provide a varying polymorphic set of parameters for the function. On instantiation, whichever arguments are supplied will be used to determine the constructor, and an object will be created and returned.

```python
class Employee:
   'Common base class for all employees'
   empCount = 0

   def __init__(self, name, salary):
      self.name = name
      self.salary = salary
      Employee.empCount += 1
```
Destructing an object is handled by python's garbage collector. Python's garbage collector runs during program execution and is triggered when an object's reference count reaches zero. An object's reference count changes as the number of aliases that point to it changes.

The "__del__(self)" function can also be applied to produce any work on object destruction.

```python
def __del__(self):
      class_name = self.__class__.__name__
      print class_name, "destroyed"
```









