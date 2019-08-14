## First-Class Functions

* In JavaScript function are treated the same way as any other value.
  - Function can be passed as argument to other function
  - A function can return another function.
  - Function can be assigned to a variable, arrray values, object values.
* Higher Order Functions
  - A function can take one or more functions as arguments or returns a function
  - map(), filter(), reducer()


#### Our own map HOF

```
function map(arr,fun){
  const newArray =[]
  
  for(let i=0; i<arr.length; i++){
       newArray[i]= fun(arr[i]);   
  }
  
  // OR
 /* 
  arr.forEach(function (value){
      newArr.push(fun(value))
  })
  */
  return newArray
}

funtion square(num){
  return num * num;
}

const myArr=[1,2,3,4]

const newMyArr = map(myArr,square)
console.log(newMyArr) // [1,4,9,16]

```
