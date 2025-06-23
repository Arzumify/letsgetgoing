# Variables and pointers

Data in Golang can be assigned to what are called **variables**. Variables are an abstraction over **pointers**, chunks of memory which can contain any data that a program wishes to store in them.

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

Go, for functions, uses what is known as **pass-by-value**. This means that when passing variables between functions, their **value** is copied over, instead of the actual variable.

For example:

```go
func main() {
	a := "Haro, Warudo!"
	fmt.Println(a)
	sub(a)
	fmt.Println(a)
}

func sub(a string) {
	a = "Bonjour, Terre!"
}
```

The output of this program would be

```go
Haro, Warudo!
Haro, Warudo!
```

If we want to, instead, be able to assign the variable dynamically, we can use **pointers**. The `&` and `*` operands can be used to turn any variable into a pointer form of itself - `&variable` transforms the variable into a pointer, and `*type` specifies that this is a pointer type.

To fix the above example:

```go
func main() {
	a := "Haro, Warudo!"
	fmt.Println(a)
	sub(&a)
	fmt.Println(a)
}

func sub(a *string) {
	// In Go, you aren't allowed to take the pointer of raw data
	// Because of this, we first assign bonjourTerre a variable
	bonjourTerre := "Bonjour, Terre!" 
	a = &bonjourTerre
}
```

This concept can be a bit complicated, as it has no easy equivalents in more high-level languages. In Python and JavaScript, an object's field can be modified like this, as objects in those languages are pointer types internally, but you cannot take the address of any arbitrary data like in Go.

A pointer is, in fact, just a number - this number corresponds to the **memory address** of the data. This does mean, however, that they cannot be sent over a network or printed directly to the terminal like normal data. To access the data behind a pointer, you can use the `*` operand to undo the pointer and get access to the raw data again.

```go
fmt.Println(*bonjourTerre) // Outputs Bonjour, Terre!
```

You can even take pointers of pointers, which can be useful for, for instance, when you need to change the address of the data you're referencing without changing the data itself.

Pointers are very powerful tools, but handle with care! Pointers are allowed to be **empty**, using the global value `nil`. If a pointer is set to `nil`, and you try to use it in your code, it will **crash**!

```go
bonjourTerre = nil
fmt.Println(*bonjourTerre) // Oh no! Nil pointer deference!
```

Because of this, it's good practice to check the data you're getting _isn't_ empty before using it.

```go
if bonjourTerre == nil {
	return // We aren't processing nil data!
}
```