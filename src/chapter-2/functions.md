# Functions and signatures

Functions are an important part of Go - in fact, they are first class citizens.

```go
func myFunction(argument1 type, argument2 type) (type, type) {
	return argument1, argument2
}
```

For return values, the brackets are only needed if there are more than one return variable, or if they are named return variables.

Sometimes, it is better in order to define a specific name for your return variables. This means instead of using `return args`, you can simply use `return`, and Go will automatically return the value of the named returns.

```go
func myFunction(argument1 type, argument2 type) (return1 type, return2 type) {
	return1 = argument1
	return2 = argument2
	return
}
```

Functions can be accessed as variables as well - and have types along with them. For instance, the type of this function:

```go
func add(a int, b int) int {
	return a + b
}
```

would be of type

```go
func(int, int) int
```

You are also able to define functions inline as objects, instead of giving them names, as such:

```go
myFunc := func(a int, b int) int {
	return a + b
}
```

You can even use function types as arguments for another function!

```go
func doMathOperation(a int, b int, operation func(int, int) int) {
	return operation(a, b)
}
```

Functions as objects like this are called **lambdas**, or **anonymous functions**.

Lastly, you are able to use `...` after a type to accept infinite of said type.

```go
func addLots(numbers int...) (answer int) {
	for number := range numbers {
		answer += number
	}
	return
}
```