## Closures


## IIFE

Immeidately Invoked Function Expression, this creates closure and doesn't add or modify global object.  It has it'w own lexical environment.

```
(function(){

  console.log("This is IIFE, executes immediately")

})();
```

**Benefits**

- To create privately accessibile variable. These variable can't be accesssed by global scope.

