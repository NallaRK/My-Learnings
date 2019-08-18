## Scope

Scope means, how long the variable lives in memory.


- Lexical scoping (var): if a variable defined using `var`, their lifetime exist within that `function{  }` body.
- Block scoping(const, let): Until the next } is reached.


, but `let`, `const` not allowed.  
`var` and `function' definations are hoisted.


var | let, const
------------ | -------------
`var` can be redeclared/overridden | `let`, `const` not allowed to redeclated in the same block?
`var` variable declarations and `function' definations are hoisted, when accessed at top, no error, but its value is 'undefined'| Not hoisted - `ReferenceError`

- JavaScript Engines, generally reads the entire file and will throw a syntax error if found.
- Any function definations will be saved in memory
- Variable initialization will NOT be run, but `var` type variable names will be declared, with value `undefined`

NOTE: 
In not strict JS world, variables can be declared event without `var`.  
These are global variables, it will pollute global scope and has lifetime untile browser window closed 
- Browser global object is the `window` object
- Node.js global object is the `global` object

From ES 2015 onwards its recommended to use let, const type variables.

#### let vs var vs IIFE

let
```
const arr=[]
for(var i=0;i<5;i++){
  arr[i]=function () { console.log(i)}
}

arr[0]()  //5 
```
Here var i scope is available outside of function and, so by the time loop ends its value is '5', so when an indexed function called, `i` inside that function block refers to outside `var i`, which already updated to '5'.

var
```
const arr=[]
for(let i=0;i<5;i++){
  arr[i]=function () { console.log(i)}
}

arr[0]()  //0  
```
Block level scope created for `let i`, so each created function refers to it own `i` variable, hence `i` value for first function 0, 2nd function 1 and so on. 

IIFE
```
const arr=[]
for(let i=0;i<5;i++){
  arr[i]=(function (x) {
            return function() { console.log(x) }
         })(i))
}
arr[0]()  //0  
```
Each function in for loop creates a closure with `i` value passed to it. So here each loop creating a new clousre environment which hold passed `i` value.

