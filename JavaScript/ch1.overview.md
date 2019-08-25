JavaScript is an interpreted language, JS engine reads code line by line and executes.
Each browser will have their own JavaScript engines, hence JS execution differs browser to browser, which leads to cross browser issues.

These browser implements standards defined by ECMAScript. 

### var, const, let
var, let and const are used to declare variables.

|                 | var                                                                                                                                                           | let                                                                                    | const                                                                                  |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| scope           | function scope                                                                                                                                                | block{ } scope                                                                         | block { } scope                                                                        |
| hoisting        | declaration hoisted with a variable value as undefined.                                                                                                       | not hoisted, referenceError  if `let` variable accessed before  declaration statement. | not hoisted, referenceError  if `let` variable accessed before  declaration statement. |
| redeclaration   | Allowed.  `var` can be redeclared multiple  times, even in the same function scope.   When accessed it refers to its  function scope recent declaration value | SyntaxError redeclaration not allowed in same block scope                              | SyntaxErrorredeclaration not allowed in same block scope                               |
| re assign value | Allowed                                                                                                                                                       | Allowed                                                                                | TypeError - `const` type variable can't be reassigned                                  |


### Types
* **Dynamic typing**  
JavaScript variables not associated with any type, they are dynamic based on its value.
* **Primitive types**
undefined
null
boolean
number
string
(symbol)    *This is introduced in ES 2015*
* **Objects**

### Type Casting
- Explicit Vs Implicit
- == Vs ===
-- Never use ==, as this provides some strange results.
- `typeof(variable)`
*NOTE:`typeof(null)` is Object*

### Truthy and Falsy Values
 **Truthy**:{}, [], Everything else
 **Falsy**: undefined, null, false, +0, -0, NaN, ""
 
 ### Primitive vs. Objects
 - Primitives are immutbale
 - Objects are muttable and stored by reference.
 
 `const obj=new Object() //using Object constructor`
 `const obj = {} //using object literal, this is prefered way`

NOTE: Object keys should be in string format, we can't use numbers.  If used, they are type casted to string.  `obj[1]` is valid, as this implict coerce into string.
`obj.1` invalid, as implicit coerce fails, and this is treated as number.

Arrays, functions in JavaScript are type of Objects.

#### Object Mutations
If an object say, `obj1` assigned to another variable say `obj2` as below
`const obj2=obj1`
Here both `obj1` and `obj2`  refers to same memory location.
- shallow copy : `const obj2=Object.assign({},obj1)`

- Deep Copy
```
function deepCopy(obj){
	const keys=Object.keys(obj)
	const newObj={}
	for(let i=0;i<keys.length;i++){
		const keys=keys[i]
		if(typeof obj[key] === 'object'){
			newObj[key]= deepCopy(obj[key])
		}else{
			newObj[key]=obj[key]
		}
	}
	return newObj
}
```
