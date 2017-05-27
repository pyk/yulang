# Hello World

In this directory there is a demonstration from a various programming 
languages on how to send a simple string to standart output.

## Python

Syntax:

```python
print('Hello World')
```

The syntax is pretty clear that it prints some string to standart output.

Tooling:

```
% python3 hello_word.py 
Hello World
```

A simple as running `python3` interpreter with file `.py`. 

## C

Syntax:

```C
#include <stdio.h>

int main(int argc, char const *argv[])
{
    printf("%s\n", "Hello World");
    return 0;
}
```

We can see that there is a header called `stdio.h` that need to be included. 
This is very explicit that we need this header, but the `printf` doesn't give
us a clue that `printf` is come from the `stdio.h` header. It should be like
`stdio.printf(format, string)`. For the basic stuff like this, I think we can
include it by default, so we don't need to include the header. It's part
from the programming language.

in C, there is a function called `main` that act as the endpoint of the 
program. it's pretty cool and very useful for large program. Love it.

For the function definition:

```
int main(int argc, char const *argv[])
```

I think the returned value should be clear that the integer is `32` bit and 
the argument should be array of string.

```yu
int32 main(string args[])
```

We should support UTF8 by default.
Oh ya, the argument and return value should be optional. we can write this as:

```yu
main() {
    
}
```

This says that the function don't take and argument and returns nothing.

For other integer data type, `C` only have `int` and `unsigned int`. We should
have copy the `Go` data type: 

```golang
uint8
uint16
uint32
uint64
int8
int16
int32
int64
```

Or

```yu
int8
int16
int32
int64
```

with optional `unsigned` keyword:

```
unsigned int8
```

For the array, there is to type of array: `static` and `dynamic`.

```
char const *argv[]
```

By default C array is a static. We can't add more alement on it.
The problem are, how to express this in syntax:

* An array of string
* An array of immutable string
* A static array of immutable string

We can propose like this (`args` is a variable name):

### An array of string

* we can add element to or remove element from the array
* we can modify the string

```yu
var args: [string]
```

### An array of constant (immutable) string

* we can add element to or remove element from the array
* we can't modify the string

```yu
var args: [const string]
```

### A constant array of string

* we can't add element to or remove element from the array
* we can modify the string

```yu
var const args: [string]
```

A constant array of constant (immutable) string

* we can't add element to or remove element from the array
* we can't modify the string

```yu
var const args: [const string]
```

So we have our complete `main` function like this:

```yu
int32 main(const args: [const string]) {
    var s: string = "Hello World"
    print(s)
    printf(format="Hello {}!", s)    
}
```
