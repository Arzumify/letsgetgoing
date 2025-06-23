# World says Hi

Great! Now that Go is installed, let's try a very simple project.

Open up your favourite coding editor[^1] and save the following file to `hello-world.go`:

```go
package main

import "fmt"

func main() {
	fmt.Println("Bonjour, Terre!")
}
```

Running `go run hello-world.go` should output to your terminal:

```
Bonjour, Terre!
```

Let's go through this example.

```go
package main
```

This defines the current package as `main`. We'll cover modules and packages more later on, but all you need to know right-now is that `main` means that this will compile to an executable.

```go
import "fmt"
```

This imports the `fmt` package from the Go standard library into your program. The `fmt` package contains functions for dealing with string formatting, and here we are using it to output to the terminal.

```go
func main() {
```

This defines a new function, called main. In `main` packages, the function `main()` will be the entrypoint for the program - the function that is executed first.

```go
    fmt.Println("Bonjour, Terre!")
```

Finally, this uses the `Println`[^2] function from `fmt` to print "Bonjour, Terre!" to the terminal.

[^1]: Popular ones include VSCode, Vim and Jetbrains-based IDEs such as Goland.
[^2]: `Println` specifically has a capital P, because in Golang, only objects beginning with capital letters are considered "public". We'll learn more about this in libraries, as well as OOP.