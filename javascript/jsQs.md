############################################
modules in javascript
```
myModule = (function(){

return{
name:"mahesh"
}
})()
myModule.name; // mahesh
```
############################################
Higher Order functions vs Pure Functions
A higher order function is a function that  takes another function as an input , returns a function or does both.

e.g., filter, map, reduce are higher order functions.

A pure function  is a function that returns a value based only of its input. Pure functions donot use variables from outer functions.
pure functions cause no mutations.
############################################
Clousures With Example
```
function createCount(){
let state = 0;
return function count(){
state += 1;
return state;
}
}
let count = createCount();
console.log(count()) //1
console.log(count()) //2
```

here count is clousure.
############################################

Functional Programming
Map, Reduce and filter
```
function addNumber(total, value){
return total + value;
}
function sum(...args){
return args.reduce(addNumber, 0)
}

sum(1,2,3)//6
```

############################################
es6 vs es5
ES5
```
let serviceProto = {
dosomething: function(){}
}
let service = Object.create(serviceProto)

console.log(service.__proto__ === serviceProto)

```
ES6
```
class Service{
dosomething(){}
}

let service = new Service();
console.log(service.__proto__ === Service.prototype)
```
############################################
Pay attention to the automatic semicolon inserting at the end of return statement
for e.g., following example will not reuturn empty object
```
function dosomething(){
let z;
return
{}
}
```
right for above program is
```
function dosomething(){
let z;
return{
}
}

```
###########################################
Print n integers using js
```
var n = 20;
iterator = Array.from(Array(n).keys());

for(key of iterator){
console.log(key);
}
```
##############################################################
```
var foo = function (){
console.log("1")
}

function foo(){
console.log("2");
}
foo() // 1
```

```
a = 2;
var a;
console.log(a) //2
```

```
console.log(a) // undefined
var a = 2; 
```
