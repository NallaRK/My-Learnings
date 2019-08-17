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

#### let vs var

```
const arr=[]
for(var i=0;i<5;i++){
  arr[i]=function () { console.log(i)}
}

arr[0]()  //5 so here lexical enviroment using var is global for all created functions, so all functions that created refers to same `i`, which is updated to 5.
```

```
const arr=[]
for(let i=0;i<5;i++){
  arr[i]=function () { console.log(i)}
}

arr[0]()  //0  lexical enviroment using i is block level, so each created function refers to it own `i` variable, hence `i` value for first function 0, 2nd function 1 and so on. 
```

