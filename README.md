
# JavaScript Interview Questions

### Table of Contents 

| No | Questions |
|-| ----------------------- |
1 | [What is the Difference between ForEach and Map?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-is-the-difference-between-foreach-and-map)  |
2 | [What is Callback, Example of Predefined callback functions?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-is-callback-example-of-predefined-callback-functions) |
3 | [What are Promises?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-are-promises) | 
4 | [Explain higher order function in javascript?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#explain-higher-order-function-in-javascript) |
5 | [What is Hoisting?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-is-hoisting) |
6 | [What is the difference between let, var, const?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-is-the-difference-between-let-var-const)
7 | [Const is unchangeable so why below code can perform?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#const-is-unchangeable-so-why-below-code-can-perform) | 
8 | [Difference between arrow and normal function?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#difference-between-arrow-and-normal-function) |
9 | [What is the Immediately invoked function in javascript?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-is-the-immediately-invoked-function-in-javascript) |
10 | [What do you mean by strict mode in javascript?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-do-you-mean-by-strict-mode-in-javascript) |
11 | [Explain call(), apply(), bind() methods?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#explain-call-apply-bind-methods) |
12 | [What is the difference between exec () and test () methods in javascript?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-is-the-difference-between-exec--and-test--methods-in-javascript)
13 | [What is currying in javascript?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-is-currying-in-javascript) |
14 | [What are Pure Functions in JS?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#what-are-pure-functions-in-js) |
15 | [Is javascript a statically typed or a dynamically typed language?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#Is-javascript-a-statically-typed-or-a-dynamically-typed-language) |
16 | [Explain Closures in JavaScript?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#Explain-Closures-in-JavaScript) |
17 | [What is memoization?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#What-is-memoization) |
18 | [What are generator functions?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#What-are-generator-functions) |
19 | [What is Object Destructuring?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#What-is-Object-Destructuring) |
20| [What is the role of deferred scripts in JavaScript?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#What-is-the-role-of-deferred-scripts-in-JavaScript)|
21| [What is the output of the following code?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#What-is-the-output-of-the-following-code)|
20 | [How to make multiple API’s call in JS at one time?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#how-to-make-multiple-apis-call-in-js-at-one-time) |
21 | [Differences between Promise.all() and Promise.allSettled() in JS?](https://github.com/erblackcode/interview-questions?tab=readme-ov-file#Differences-between-Promise.all()-and-Promise.allSettled()-in-JS) |

## Questions

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

### Is javascript a statically typed or a dynamically typed language?

JavaScript is a `dynamically typed` language. In a dynamically typed language, the type of a variable is checked during `run-time` and in statically, where the type of a variable is checked during compile-time.

For example, a variable that is assigned a number type can be converted to a string type:

```javascript
var a = 23;
var a = "Hello World!";
```

### Explain Closures in JavaScript?
Closures are an ability of a function to remember the variables and functions that are declared in its outer scope.

Let’s understand closures by example:

```javascript
function randomFunc(){
  var obj1 = {name:"Vivian", age:45};

  return function(){
    console.log(obj1.name + " is "+ "awesome"); // Has access to obj1 even when the randomFunc function is executed

  }
}

var initialiseClosure = randomFunc(); // Returns a function

initialiseClosure(); 
```
Let’s understand the code above,

The function randomFunc() gets executed and returns a function when we assign it to a variable:
```javascript
var initialiseClosure = randomFunc();
```
The returned function is then executed when we invoke initialiseClosure:
```javascript
initialiseClosure(); 
```
The line of code above outputs “Vivian is awesome” and this is possible because of closure.

```javascript
console.log(obj1.name + " is "+ "awesome");
```

When the function randomFunc() runs, it seems that the returning function is using the variable obj1 inside it:

Therefore randomFunc(), instead of destroying the value of obj1 after execution, saves the value in the memory for further reference. This is the reason why the returning function is able to use the variable declared in the outer scope even after the function is already executed.

`This ability of a function to store a variable for further reference even after it is executed is called Closure.`

### What is memoization?
Memoization is a form of caching where the return value of a function is cached based on its parameters. If the parameter of that function is not changed, the cached version of the function is returned.
Let’s understand memoization, by converting a simple function to a memoized function:

```javascript
function addTo256(num){
  return num + 256;
}
addTo256(20); // Returns 276
addTo256(40); // Returns 296
addTo256(20); // Returns 276
```

In the code above, we have written a function that adds the parameter to 256 and returns it.
When we are calling the function addTo256 again with the same parameter (“20” in the case above), we are computing the result again for the same parameter.

**Why Memoization -** Computing the result with the same parameter, again and again, is not a big deal in the above case, but imagine if the function does some heavy-duty work, then, computing the result again and again with the same parameter will lead to wastage of time.

This is where memoization comes in, by using memoization we can store(cache) the computed results based on the parameters. If the same parameter is used again while invoking the function, instead of computing the result, we directly return the stored (cached) value.

Let’s convert the above function addTo256, to a memoized function:

```javascript
function memoizedAddTo256(){
  var cache = {};

  return function(num){
    if(num in cache){
      console.log("cached value");
      return cache[num]
    }
    else{
      cache[num] = num + 256;
      return cache[num];
    }
  }
}
var memoizedFunc = memoizedAddTo256();

memoizedFunc(20); // Normal return
memoizedFunc(20); // Cached return
```

In the code above, if we run the memoizedFunc function with the same parameter, instead of computing the result again, it returns the cached result.

`memoized function is same as pure function - both are return the same value for the same input`

### What are generator functions?
Introduced in the ES6 version, generator functions are a special class of functions.

They can be stopped midway and then continue from where they had stopped.

Generator functions are declared with the function* keyword instead of the normal function keyword:
```javascript
function* genFunc(){
  // Perform operation
} 
```
In the case of generator functions, when called, they do not execute the code, instead, they return a generator object. This generator object handles the execution
```javascript
function* genFunc(){
  yield 3;
  yield 4;
}
genFunc(); // Returns Object [Generator] {}
```
The generator object consists of a method called next(), this method when called, executes the code until the nearest yield statement, and returns the yield value.

For example, if we run the next() method on the above code:
```javascript
genFunc().next(); // Returns {value: 3, done:false}
```
As one can see the next method returns an object consisting of a value and done properties.  Value property represents the yielded value. Done property tells us whether the function code is finished or not. (Returns true if finished).

Generator functions are used to return iterators. Let’s see an example where an iterator is returned:
```javascript
function* iteratorFunc() {
  let count = 0;
  for (let i = 0; i < 2; i++) {
      count++;
      yield i;
  }
  return count;
}

let iterator = iteratorFunc();
console.log(iterator.next()); // {value:0,done:false}
console.log(iterator.next()); // {value:1,done:false}
console.log(iterator.next()); // {value:2,done:true}
```
As you can see in the code above, the last line returns done:true, since the code reaches the return statement

### What is Object Destructuring?

Object destructuring is a new way to extract elements from an object or an array.
```javascript
const classDetails = {
  strength: 78,
  benches: 39,
  blackBoard:1
}

const {strength:classStrength, benches:classBenches,blackBoard:classBlackBoard} = classDetails;

console.log(classStrength); // Outputs 78
console.log(classBenches); // Outputs 39
console.log(classBlackBoard); // Outputs 1
```
### What is the role of deferred scripts in JavaScript?
The processing of HTML code while the page loads are disabled by nature till the script hasn't halted. Your page will be affected if your network is a bit slow, or if the script is very hefty. When you use Deferred, the script waits for the HTML parser to finish before executing it. This reduces the time it takes for web pages to load, allowing them to appear more quickly.

### What is the output of the following code?
```javascript
const b = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

for (let i = 0; i < 10; i++) {
  setTimeout(() => console.log(b[i]), 1000);
}

for (var i = 0; i < 10; i++) {
  setTimeout(() => console.log(b[i]), 1000);
}
```

**Answer -**
```javascript
1
2
3
4
5
6
7
8
9
10
undefined
undefined
undefined
undefined
undefined
undefined
undefined
undefined
undefined
undefined
```
`The main difference is scoping rules. Variables declared by var keyword are scoped to the immediate function body (hence the function scope) while let variables are scoped to the immediate enclosing block denoted by { } (hence the block scope)`

An experiment that is possible is to make let behave like var. To make let behave like var, you can use (and run) the code below.

```javascript
let i;
for (i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1);
}
```

### How to make multiple API’s call in JS at one time? 
#### Two independant calls, but I need the data from both before moving on
So maybe I need data from two sources, but I don't want the subsequent code to run till both requests have completed.

I could just use await and do them one by one.
```javascript
async function getData(){
    const url1 = //...
    const url2 = //...

    const response1 = await fetch(url1)
    const data1 = await response1.json()

    const response2 = await fetch(url2)
    const data2 = await response1.json()

    // do what you want with data1 and data2 here
}
getData()
``` 

This works great the only downside is the await keyword pauses the function so the second request won't happen till the first one finishes. We can have them both run at the same time but make sure the function doesn't continue till they both complete using Promise.all().

`As promise.all() takes array of promisses as an input and return the promise as an output`

`it always have to use when you sure all promises will get resolve, if any promise will fail to resolve it will give you an error`

```javascript
async function getData(){
    const url1 = //...
    const url2 = //...

    const responses = await Promise.all([fetch(url1), fetch(url2)])

    const data1 = await responses[0].json()
    const data2 = await responses[1].json()

    // do what you want with data1 and data2 here
}

getData()
```
Promise.all returns a promise that doesn't resolve till all promises in the array passed in are resolved (the two fetch calls). So both fetch calls are initiated but the function is paused on the Promise.all not the individual fetches. This works well if one of the two requests take a really long time that it would speed things up to have both requests made right away.

### Differences between Promise.all() and Promise.allSettled() in JS?

**Promise.all() -**
```javascript
// **** When all promises are resolved ****

const p1 = Promise.resolve(3);
const p2 = 1337;
const p3 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("foo");
  }, 100);
});

// promise.all will return new promise and from 'then' it will resolved
Promise.all([p1, p2, p3]).then((values) => {
  console.log(values); // [3, 1337, "foo"]
});

// **** when from of all some of faild ****

// All values are non-promises, so the returned promise gets fulfilled
const p = Promise.all([1, 2, 3]);

// The only input promise is already fulfilled,
// so the returned promise gets fulfilled
const p2 = Promise.all([1, 2, 3, Promise.resolve(444)]);

// One (and the only) input promise is rejected,
// so the returned promise gets rejected
const p3 = Promise.all([1, 2, 3, Promise.reject(555)]);

// Using setTimeout, we can execute code after the queue is empty
// without resolving promises printing all so they are returing promises
setTimeout(() => {
  console.log(p);
  console.log(p2);
  console.log(p3);
});

// Logs:
// Promise { <state>: "fulfilled", <value>: Array[3] }
// Promise { <state>: "fulfilled", <value>: Array[4] }
// Promise { <state>: "rejected", <reason>: 555 }
```

`Promise.all will reject as soon as one of the Promises in the array rejects. And when we will resolve that promises will get error in catch() callback function`

**Promise.allSettled() -**
```javascript
Promise.allSettled([
  Promise.resolve(33),
  new Promise((resolve) => setTimeout(() => resolve(66), 0)),
  99,
  Promise.reject(new Error("an error")),
]).then((values) => console.log(values));

// [
//   { status: 'fulfilled', value: 33 },
//   { status: 'fulfilled', value: 66 },
//   { status: 'fulfilled', value: 99 },
//   { status: 'rejected', reason: Error: an error }
// ]
```

`Promise.allSettled will never reject - it will resolve once all Promises in the array have either rejected or resolved.`

#### Difference - 

Their resolve values are different as well. Promise.all will resolve to an array of each of the values that the Promises resolve to - eg [Promise.resolve(1), Promise.resolve(2)] will turn into [1, 2]. Promise.allSettled will instead give you [{ status : 'fulfilled', value: 1 }, { status : 'fulfilled', value: 2 }].

```javascript
Promise.all([Promise.resolve(1), Promise.resolve(2)])
  .then(console.log);
Promise.allSettled([Promise.resolve(1), Promise.resolve(2)])
  .then(console.log);
```

If one of the Promises rejects, the Promise.all will reject with a value of the rejection, but Promise.allSettled will resolve with an object of { status: 'rejected', reason: <error> } at that place in the array.

```javascript
Promise.all([Promise.reject(1), Promise.resolve(2)])
  .catch((err) => {
    console.log('err', err);
  });
Promise.allSettled([Promise.reject(1), Promise.resolve(2)])
  .then(console.log);
```
 
