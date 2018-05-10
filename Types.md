
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
