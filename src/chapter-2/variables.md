# Variables

Data in Golang can be assigned to what are called **variables**. Variables are an abstraction over **pointers**, chunks of memory which can contain any data that a program wishes to store in them. We'll discuss pointers in a bit, don't worry!

Go is a memory-collected language. This means that all variables are automatically destroyed when you stop using them, meaning you can focus on the core logic of the program and not have to worry about cleaning up after yourself. 

To assign a variable, the `var` keyword is used.

```go
var variableName string
```

This creates a new variable of type `string`.

You are also able to assign content using the `=` operand:

```go
var variableName string = "Bonjour, Terre!"
```

However, due to type inference, the `string` isn't needed when assigning like this, turning it into simply

```go
var variableName = "Bonjour, Terre!"
```

For convenience, Go also includes the `:=` operand, which eliminates the need for `var`.

```go
variableName := "Bonjour, Terre!"
```

However, typing cannot be explicit and variables cannot be empty when doing this.

To assign a value to an existing variable, simply use the `=` operand.

```go
var variableName string
variableName = "Bonjour, Terre!"
```