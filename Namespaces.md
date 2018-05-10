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
