
# JavaScript Interview Questions


### What is the Difference between ForEach and Map? 

map returns a new array with the results of the function applied to each element, while forEach does not return anything. 

| forEach()              | map()         |
| ----------------- | ------------------------------------------------------------------ |
| The forEach() method does not returns a new array based on the given array  | The map() method returns an entirely new array  |
| The forEach() method returns “undefined“ | The map() method returns the newly created array according to the provided callback function |
| The forEach() method doesn’t return anything hence the method chaining technique cannot be applied here | With the map() method, we can chain other methods like, reduce(),sort() etc |
| It is not executed for empty elements | It does not change the original array |

**Example:** const test = [1, 2, 3] 

console.log(test.map(ele => ele)) 

console.log(test.forEach(ele => ele)) 

**OutPut** of A – it will be [1,2,3] because map returns array but for B- is undefind because forEach return nothing 

### What is Callback, Example of Predefined callback functions? 

JavaScript is built to handle asynchronous programming, allowing it to manage multiple tasks at once. Callbacks are important in JavaScript as they enable you to execute code after an asynchronous task finishes.

**What -** A callback is a function passed as an argument to another function, which gets invoked after the main function completes its execution. You pass the callback function to the main function as an argument, and once the main function finishes its task.

**Why-** Callbacks are essential for managing the outcomes of asynchronous tasks without blocking the program’s execution. Asynchronous tasks, like network requests or database queries, take time to finish. If these tasks were synchronous, the program would halt until they’re done, resulting in a sluggish user experience. 

With callbacks, though, you can keep the program running while these tasks happen in the background. When the task finishes, the callback function handles the result. This ensures the program stays responsive, enhancing the user experience. 

### What are Promises?

Promises are used to handle asynchronous operations in javascript. 
 
Before promises, callbacks were used to handle asynchronous operations. But due to the limited functionality of callbacks, using multiple callbacks to handle asynchronous code can lead to unmanageable code. 
 
Promise object has four states - 
- **Pending -** Initial state of promise. This state represents that the promise has neither been fulfilled nor been rejected, it is in the pending state.
- **Fulfilled -** This state represents that the promise has been fulfilled, meaning the async operation is completed.
- **Rejected -** This state represents that the promise has been rejected for some reason, meaning the async operation has failed.
- **Settled -** When state either fulfilled or rejected.

Promises are used to handle asynchronous operations like server requests, for ease of understanding, we are using an operation to calculate the sum of three elements. 

### Example

```javascript
function sumOfThreeElements(...elements){ 
  return new Promise((resolve,reject)=>{ 
    if(elements.length > 3 ){ 
      reject("Only three elements or less are allowed"); 
    } 
    else{ 
      let sum = 0; 
      let i = 0; 
      while(i < elements.length){ 
        sum += elements[i]; 
        i++; 
      } 
      resolve("Sum has been calculated: "+sum); 
    } 
  }) 
} 
sumOfThreeElements(4, 5, 6).then(result=> console.log(result)).catch(error=> console.log(error)); 
```

### Explain higher order function in javascript? 
Higher order functions (HOFs) in JavaScript are functions that can do at least one of the following

- Accept other functions as arguments.
- Return a function as a result.

### Example

```javascript
function higherOrder(fn) { 

 fn();  

}  

higherOrder(function() { console.log("Hello world") }); 

function higherOrder2() {  

return function() {  

return "Do something";  

} }  

var x = higherOrder2();  

x() // Returns "Do something" 
```
Some Predefined JS HOC function: **Map**, **Reduce**, **Filter**. 


### What is Hoisting?
Hoisting is the default behavior in JavaScript where variable and function declarations are moved to the top of their respective scopes during the compilation phase. 

### Example 1

```javascript
// Hoisting 
function codeHoist() { 
    a = 10; 
    let b = 50; 
} 
codeHoist(); 
 
console.log(a); // 10 
console.log(b); // ReferenceError : b is not defined  
```
**Explanation –** The interpreter sees this differently, the above code is seen like below, where ‘a’ is the global variable but b has local scope so that b will give referenceError. 

```javascript
Var a; 

function codeHoist() { 
    a = 10; 
    let b = 50; 
} 
codeHoist(); 
 
console.log(a); // 10 
console.log(b); // ReferenceError : b is not defined  
```

### Example 2
```javascript
// Hoisting 

// var code (global) 
console.log(name); // undefined 
let name = 'Mukul Latiyan'; 
```

**Explanation-** The interpreter sees this differently, the above code is seen like below, Hositing is working only for the variable declaration not for initializing

```javascript
let name; 
console.log(name); // undefined 
name = 'Mukul Latiyan'; 
```

### Example 3
```javascript
fun() // Calling the expression 
 
let fun = () =>{ // Declaring 
    let name = 'Mukul Latiyan'; 
    console.log(name); 
} 
```

### What is the difference between let, var, const? 

| keyword             | const          | let | var |
| ----------------- | ----------------------- | --------------------- | ----------------|
Global scope   | no  | no | yes | 
Function scope   | yes | yes | yes |
Block scope  | yes | yes | no | 
Can be reassigned  | no | yes | yes |

### Example

**For let -**
```javascript
let a = 10 
if (true) { 
    let a = 9 
    console.log(a) // It prints 9 
} 
console.log(a) // It prints 10 
```

**For var -**
```javascript
var a = 10 
if (true) { 
    var a = 9 
    console.log(a) // It prints 9 
} 
console.log(a) // It prints 9 
```

**For const -**
```javascript
const a = 10 
if (true) { 
    const a = 9 
    console.log(a) // Type Error: Assignment to constant variable 
} 
console.log(a) // Type Error: Assignment to constant variable 
```

### Const is unchangeable so why below code can perform? 

```javascript
const a = { 
    prop1: 10, 
    prop2: 9 
} 
 
// It is allowed 
a.prop1 = 3 

console.log(a); 
```

**Explanation -** When you're adding to an array or object, you're not re-assigning or re-declaring the constant; it's already declared and assigned. You're just adding to the list of elements or properties to which the constant points. 

### Difference between arrow and normal function? 
Arrow functions were introduced in the ES6 version of javascript. They provide us with a new and shorter syntax for declaring functions. Arrow functions can only be used as a function expression. 

Regular function is used to declare by putting ‘function’ keyword before putting the name of function. 

Arrow functions do not have their own ‘this’ unlike regular functions. 

```javascript
let user = { 
        name: "GFG", 

        gfg1:() => { 
            console.log("hello " + this.name); // no 'this' binding here 
        }, 

        gfg2(){     
            console.log("Welcome to " + this.name); // 'this' binding works here 
        } 
    }; 

    user.gfg1(); 
    user.gfg2(); 
```

By general definition, this keyword always refers to the object that is calling the function. As you can see in the code above, user.gfg2() returns name since this keyword refers to the object calling the function. 

 

In the arrow functions, there is no binding of this keyword. This keyword inside an arrow function does not refer to the object calling it. It rather inherits its value from the parent scope which is the window object in this case. Therefore, in the code above, user.gfg1() returns the window object. 

### What is the Immediately invoked function in javascript? 

An Immediately Invoked Function (known as IIFE and pronounced as IIFY) is a function that runs as soon as it is defined. 

```javascript
Syntax of IIFE: 

(function () {  

   // Do something;  

})(); 
```

### What do you mean by strict mode in javascript? 
Strict mode is a developer mode where debugging becomes a lot simpler.  Thus programmer's chances of making an error are lowered. 

Characteristics of strict mode in javascript - 

- Duplicate arguments are not allowed by developers. 
- In strict mode, you won't be able to use the JavaScript keyword as a parameter or function name. 
- The 'use strict' keyword is used to define strict mode at the start of the script. Strict mode is supported by all browsers. 
- Engineers will not be allowed to create global variables in 'Strict Mode 

### Explain call(), apply(), bind() methods? 

call() method takes arguments separately whereas, apply() method takes arguments as an array. 

bind() method returns new function; to get the actual result we need to consume function which is returned by bind. 

### What is the difference between exec () and test () methods in javascript? 

- test () and exec () are RegExp expression methods used in javascript.  

- We'll use exec () to search a string for a specific pattern, and if it finds it, it'll return the pattern directly; else, it'll return an 'empty' result. 

- We will use a test () to find a string for a specific pattern. It will return the Boolean value 'true' on finding the given text otherwise, it will return 'false' 

### What is currying in javascript? 

Currying is an advanced technique to transform a function of arguments n, to n functions of one or fewer arguments.

Example of a curried function: 
```javascript
function add (a) { 
 return function(b) {  
    return a + b;  
    }  
}  

add(3)(4) ;
```

### What are Pure Functions in JS? 
A Pure Function is a function (a block of code) that always returns the same result if the same arguments are passed. It does not depend on any state or data change during a program’s execution. Rather, it only depends on its input arguments. 

### How to make multiple API’s call in JS at one time? 

 
