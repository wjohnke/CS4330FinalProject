# Properties

## C#
Properties in C# are used to encapsulate data. They use the keyword "value" to set whichever value the setter is supposed to set.
They are implemented as such:
```c#
private string _s;
public string YourProperty
{
  get { return _s; }
  set { _s = value; }
}
```

And can contain other expressions than just assignment:

```c#
set
        {
            if ((value > 0) && (value < 13))
            {
                month = value;
            }
        }
```

Getters must return the value of the property, i.e. the "value" that was set.
```c#
class Person
{
    private string name;  // the name field
    public string Name    // the Name property
    {
        get
        {
            return name;
        }
    }
}
```
And they must be called as so:
```c#
Person person = new Person();
//...

System.Console.Write(person.Name);  // the get accessor is invoked here
```
Backing variables can be set in order to ensure that they are only modified by calling the property, as such:
```c#
public class Date
{
    private int month = 7;  // Backing store

    public int Month
    {
        get
        {
            return month;
        }
        set
        {
            if ((value > 0) && (value < 13))
            {
                month = value;
            }
        }
    }
}
```
Using calculations as properties, as opposed to providing methods is also possible.

## Python

Encapsulation is not as heavily used in python, but can be provided in properties using methods like: get_"varName" and set_"varName"
Attributes can be declared private to enable use of getters and setters through the ``self._x``, which would make x private.

If a variable is made public, no getters or setters are required (they are built in), and the variable can be accessed directly.

Backing variables can be utilized by adding the underscore "_" before the variable.

Computed properties could be implemented as such (noted under the get_color(self) function):

```python
class Widget(object):
    def __init__(self, arg=None):
        if arg:
            self.color_data = arg
        else:
            self.color_data = (0,0,0)

    def get_color(self):
        if type(self.color_data) is tuple:
            return self.color_data
        else:
            return str_to_tuple(self.color_data)

    def set_color(self, arg):
        self.color_data = arg

    # create property object to dispatch 'get' and 'set' methods
    # NOTE: "color" is a class attribute, not an instance attribute
    color = property(get_color, set_color)
```


