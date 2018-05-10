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





