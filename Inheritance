# Inheritance

## C#

Inheritance is covered in C#, and is similar to Java. Static constructors, instance constructors, as well as Finalizers are all not
inherited by any subclass that extends a superclass.

If composition is used, then the composed class can see private members of the nested outer class. Otherwise, no private properties can be accessed or viewed.
Example:
```c#
using System;

public class A 
{
   private int value = 10;

   public class B : A
   {
       public int GetValue()
       {
           return this.value;
       }     
   }
}

public class C : A
{
//    public int GetValue()
//    {
//        return this.value;
//    }
}

public class Example
{
    public static void Main(string[] args)
    {
        var b = new A.B();
        Console.WriteLine(b.GetValue());
    }
}
// The example displays the following output:
//       10
```


## Python

Python supports inheritance, syntactically shown as:

```python
class DerivedClassName(BaseClassName):
    pass
```

Or a more elaborate example:

```python
class Person:

    def __init__(self, first, last):
        self.firstname = first
        self.lastname = last

    def Name(self):
        return self.firstname + " " + self.lastname

class Employee(Person):

    def __init__(self, first, last, staffnum):
        Person.__init__(self,first, last)
        self.staffnumber = staffnum

    def GetEmployee(self):
        return self.Name() + ", " +  self.staffnumber

x = Person("Marge", "Simpson")
y = Employee("Homer", "Simpson", "1007")

print(x.Name())
print(y.GetEmployee())
```
