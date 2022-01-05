# Hello World!

```Go
package main

import (
	"fmt"
)

func main() {
	fmt.Println("hello, world!")
}
```

The above is the classic hello world example, which is a good
introduction to the language syntax.

The first line is defining the `package`, which Go programs are
constructed by linking packages together. According to the specification
"A complete program is created by linking a single, unimported packaged
called the *main package* with all the packages it imports, transitively.
The main package must have the name `main` and declare a function `main`
that takes no arguments and returns no value." This important to remember
and why we declare the package in the above example as `main`.

The next line is *one* of Go's many ways of importing other packages. I
say one way, because there are various other ways to import, like the
common way below.

```Go
package main

import (
	f "fmt"
)

func main() {
	f.Println("hello, world!")
}
```

This is one way of importing, which assigns the imported packaged to the
variable defined in the import statement (in this case `f`). You can find
out more about import declarations in the specification under the
`Packages` section.

After the import statment is the declaration of `func main` or the main
function. It is important to remember from the earlier information that
the main function takes no arguments and returns no value.

The last line in the hello world example is `fmt.Println("hello,
world!")`, which is an example of input/output (I/O) in Go. In this case
we are using the `fmt` package, which contains various formatted I/O
functions. Another way we could do the hello world example is as follows.

```Go
package main

import (
	"fmt"
)

func main() {
	fmt.Printf("Hello %s\n", "world!")
}
```

One thing to note is that the `Printf` function does not add a newline
(`\n`) to the end of the input like the `Println` function does.

So how do we turn this Go code into a program? Go come with it a
toolchain, which contains a `build` command for compiling and creating a
binary in the local directory. There is also the `install` command which
does the same as `build`, but puts the binary in the `$GOBIN` location.

If you tried one of the above commands right now, you will get the
following output.

```
go: cannot find main module, but found .git/config in ...
        to create a module there, run:
        cd .. && go mod init
```

This is the compiler giving you a hint, and in this case gives you the
solution.


Before we can run either commands, we need to create a module. Don't
worry about the details (covered in chapter on modules), for now just
understand they are required, used for dependency management, and are the
name for the compiled binary unless specified otherwise. To create a new
module, we run the command `go mod init example.com/hello-world`. Let's
run `go build`, so the compiled binary is stored in our local directory
(under the name `hello-world`). To run the binary, enter `./hello-world`.

Related:

* Go Programming Language Specification
	<https://go.dev/ref/spec#Source_file_organization>
* Package `fmt`
	<https://pkg.go.dev/fmt>
