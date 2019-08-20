# Objects in JavaScript

An Object is dynamic collection of properties and every property has a key (type string) that is unique within that object.

Object literal representaion is preferred way to create objects in JavaScript, JS also provides constructor.
### Object literal:
```
  var obj={
    name:"person name",
    age:99,
  };
  
```
### Object constructor:
```
var obj=new Object();
```

### get, set and delete

- getting value from a object's key: console.log(obj.name)
- setting value to a object's key  : obj.name="some name";
- deleting whole key from object   : delete obj.age;

## Object Methods:

### Object.create()
    Object.create(null)
    
### Object.assign()
