# New Binary
As programmer, I want to write and run my code as fast as possible.
I mean fast is there is no headache on between compiling the program
and running the program.

Simple as:

```
yu run hello.yu
```

With the content of `hello.yu` like the following:

```
import io


```

What's the good name of the package to store `print` yeah?
`standart` or `std`?

Let's use the ideas from [golang](https://golang.org/pkg/fmt/).

```
import fmt

int main() {
    fmt::println("hello world");
    fmt::printf("{} {}", "yes", "test");
    return 0;
}
```

The problem is how do we compile `hello.yu` to machine code and run it?
Let's find out about how to compile it first.
