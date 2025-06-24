# Boolean Logic

Logic in Go is mostly the same as any other language - the `if else` syntax we all know and love is very much the standard here.

Booleans in Go are a type - `bool`, and can have the values `true` and `false`.

```go
var condition bool
```

By default, empty boolean variables are of type `false`. Keep this in mind; as it's good practice to have the `true` condition be the position in which the action _does_ rather than _does not_ occur, such that if the variable is accidentally left uninitialized nothing undesirable will happen.

The `if` keyword is used to check if a boolean is true.

```go
var condition = true
if condition {
	fmt.Println("Bonjour, Terre!")
}
```

To _reverse_ any boolean condition, we can use the `!` keyword.

```go
var condition = false
if !condition {
	fmt.Println("Bonjour, Terre?")
}
```

The equivalents of `and` and `or` in Go are `&&` and `||`, respectively:

```go
if true && true {
	true
}

if true && false {
	false
}

if true || false {
	true
}
```

Brackets can be used as logical brackets, in order to make conditions follow a certain order of execution.

```go
if true || (true && false) {
	true
}

if (true || true) && false {
	false
}
```

Of course, not everything is a boolean. When you must compare two objects with each other, you should use the `==` operator.

```go
if "string" == "string" {
	true
}
```

To do the opposite, `!=` should be used. This is equal to using `!(x == y)`, but is more concise.

```go
if "string" != "another string" {
	true
}
```

A side note is that during `if`, you are able to assign variables within the `if` that can only be accessed within the function and the condition. After that, you need to use a semicolon to set the condition.

For example:

```go
if answer := add(1, 2); answer == 3 {
	// The answer is 3
	fmt.Println(answer)
}
```