## Prototypal Inheritance

What is a prototype:
obj.\__proto\__

Each object stores a referernce to its prototype.

Most primitive types have object wrappers.  So if any method called on primitive type variables, respective Object wrapper \__proto\__ methods will be called.
Ex: `"FooBar".toString(); // String Object proto method toString called`

- String()
- Number()
- Boolean()
- Object()
- (Symbol())
