# A quick tour of Go

## The compiler

Go is a compiled language. This means that unlike python, where code is ran line-by-line and parsed on-the-fly, Go builds the entire program, all at once, into a single executable.

The program that does this process is the Go compiler, which is invoked using the command `go build`.

This command won't do anything until we have a project to build, though, so stick around till Chapter 2 where we build our first program.

## The linter

Go's syntax is designed such that it can be easily formatted neatly and tidily. To do this, the `go fmt`[^1] command is used.

All the examples that we will be giving in this book will be formatted using `go fmt`, and it's good practice to format all your files using it once you're done.

## The vetter

The Go vetter is designed to automatically search for mistakes that you might have made in any of your code. This command is invoked using `go vet`, similarly to `go build`.

## The tester

Golang comes with a comprehensive unit testing framework, invoked using `go test`. Usage of this testing framework will be covered later.

## Module management

All Go code is broken down into "modules". To manage modules, the `go mod` command is used. `go mod init` creates modules, `go mod tidy` tidies their libraries, and `go mod download` dowloads libraries to the Go library cache.

## Libraries galore

Golang has a wide array of community-made libraries, which are added and installed to a project automatically using `go mod tidy`. However, you can also install them manually using the `go get` command.

[^1] To only format a single file, use `gofmt file.go`.

## External apps

Not only is the `go` command great for building your code, it can also fetch code and act as it's own source-based package manager. Use `go install` to install packages built using Go straight to your machine.