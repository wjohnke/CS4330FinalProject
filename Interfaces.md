# Interfaces/Protocols

## C#

Interfaces in C# work very similarly to Java, and can be defined as:
```c#
interface IEquatable<T>
{
    bool Equals(T obj);
}
```

This will make any class that implements IEquatable<T>, also be forced to implement Equals.
Interfaces can contain methods, properties, events, indexers, or any combination of those four member types, but cannot be instantiated themselves.

The actual implementation of the methods then falls onto the class as such:

```c#
public class Car : IEquatable<Car>
{
    public string Make {get; set;}
    public string Model { get; set; }
    public string Year { get; set; }

    // Implementation of IEquatable<T> interface
    public bool Equals(Car car)
    {
        if (this.Make == car.Make &&
            this.Model == car.Model &&
            this.Year == car.Year)
        {
            return true;
        }
        else
            return false;
    }
}
```

In C#, interfaces can also provide additional accessors for properties of the interface.

## Python

Interfaces are not a keyword in python, so informal interfaces are implemented through the use of protocols. If a class defines a certain protocol,
which is defined throug "__ex__", such as "__init__" or "__iter__" or "__len__", it can be treated as an object of that protocol. If something
performs like the things it is interfacing with, it will be treated as that same interface.

Implementation looks like:

```python
class Team:
    def __init__(self, members):
        self.__members = members

    def __len__(self):
        return len(self.__members)

    def __contains__(self, member):
        return member in self.__members


justice_league_fav = Team(["batman", "wonder woman", "flash"])

# Sized protocol
print(len(justice_league_fav))

# Container protocol
print("batman" in justice_league_fav)
print("superman" in justice_league_fav)
print("cyborg" not in justice_league_fav)
```

Forced protocols/interfaces can also be implemented, through the use of Abstract Base Classes (ABC), as such:
```python
import abc

class Bird(abc.ABC):
    @abc.abstractmethod
    def fly(self):
        pass
```
This forces any classes that extend (implement in our case) the specific class, to also implement the given methods.
