# Intro to YML (aka YAML)
## List
```yml
- "Red iPhone"  
- "Black iPhone"
- "White iPhone"
- "Teal iPhone"
- "Yellow iPhone"
- "Purple iPhone"
```

## Dictionary
- key/value pairs
```yml
# equivalent to:
# {Cat:{Name:"Kitty", Weight:"4.2kg", "Age:5"}}
Cat:
	Name: "Kitty"
	Weight: "4.2kg"
	Age: 5
```
- Nested Dictionary
```yml
Phone:
	Color: "white"
	Model:
		Name: "iphone 5"
		Release: 2012
```
