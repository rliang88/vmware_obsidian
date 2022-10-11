- function receivers in Golang:
	- https://stackoverflow.com/questions/34031801/function-declaration-syntax-things-in-parenthesis-before-function-name
```go
func (s *GracefulServer) BlockingClose() bool {
    ...
}
// s *GracefulServer is the thing calling the method
// this is sorta how we do object oriented programming
// in go
```

- `interface{}`
	- https://stackoverflow.com/questions/23148812/whats-the-meaning-of-interface#:~:text=interface%7B%7D%20means%20you%20can,have%20value%20of%20any%20type.
	- `interface{}` is the **empty interface**
		- equivalent to `any`
	- all types satisfy the empty interface!!