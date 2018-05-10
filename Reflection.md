# Reflection

## C#

C# handles reflection, the ability of a programming language to introspect on its own code at runtime, through various methods.
The GetType method returns the type of a variable:
```c#
// Using GetType to obtain type information:
int i = 42;
System.Type type = i.GetType();
System.Console.WriteLine(type);
```
Implementing reflection in C# requires a two-step process. You first get the “type” object, then use the type to browse members such as “methods” and “properties.”

Various methods allow you to access instance types and methods:

```c#
// dynamically load assembly from file Test.dll
Assembly testAssembly = Assembly.LoadFile(@"c:\Test.dll");
//To create an instance of the calculator class:

// get type of class Calculator from just loaded assembly
Type calcType = testAssembly.GetType("Test.Calculator");

// create instance of class Calculator
object calcInstance = Activator.CreateInstance(calcType);
//And access its members (the following examples illustrate getting values for the public double Number property):

// get info about property: public double Number
PropertyInfo numberPropertyInfo = calcType.GetProperty("Number");

// get value of property: public double Number
double value = (double)numberPropertyInfo.GetValue(calcInstance, null);

// set value of property: public double Number
numberPropertyInfo.SetValue(calcInstance, 10.0, null);
```
Reflection in C# is capable of use because:
"The main class for reflection is the System.Type class, which is an abstract class representing a type in the Common Type System (CTS). When you use this class, you can find the types used in a module and namespace and also determine if a given type is a reference or value type."

## Python

