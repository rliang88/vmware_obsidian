# Go: Getting Started
**What is go good at?**
- best at building web services and web applications
- go comes with built in concurrency functions

**Entry Point of Go application**
- `package main` -> `func main()` 
- every project regardless of the module name, needs to have a main package

- Every package that gets imported MUST be used!!
	- This helps with code maintanability by forcing you to be minimal

- Go enforces automatic semicolon insertion, so have to format code a certain way

**Running a Go Application**
- run a specific file with:
	- `go run <relative path to file>`
- run the application with `main.go`  as the entrypoint
	- `go run <relative path to main.go`
	- `go run <module name>`

- go supports automatic memory managment like memory allocation and garbage collection

## Variables
- variables declared MUST be used!
- `var <name> <datatype> = <value>`
- syntax for go to assume the datatype:
	- `<name> := <value>`

**Pointers**
- `nil` is go for an uninitialized pointer
- Go does not allow pointer arithmetic!!

**Address Of Operator** 
- used to get the memory address of a variable stored in stack, not heap
- can create a pointer out of a variable that was not originally a pointer

## Constants
- constants must be able to be evaluated at compile time

**Iotas**
- iotas are constants that stay unique within the constant block 

**Constant Expressions**
- expressions assigned to a constant that must be able to be defined at compile time

ex:
```go
const (
	first = iota
	second = iota + 6
)

// output: 
// first = 0
// second = 8
```

## Collections
- Arrays, Slices, and Maps

**Arrays**
- Arrays are fixed length structure of a similar datatype

**Slices**
- Slices are dynamically lengthed arrays
- slices can be built atop arrays but are shallow copies

**Maps**
- key value pairs

**Structs**
- allow us to associate disparate datatypes together

## Functions
**Parameters in Functions**
- parameters that are passed into a function don't have to be used in the function

`_` = write only variable (wildcard that gets ignored)