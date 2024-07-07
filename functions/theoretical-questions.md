## Theoretical Questions

#### Q1:What is function declaration/ function defination ? 

**Answer**:The following code snippet illustrates function declaration/function defination 

```javascript
function square(num) {

  return num * num;

}
```

#### Q2:What is function expression ?

**Answer**: The following code snippet illustrates function expression 

```javascript
const square = function (num) {

  return num * num;

};
```

#### Q3:What are anonymous functions ? 

**Answer**: Anonymous functions in JavaScript are functions that are defined without a name

```javascript
// Anonymous function passed as an argument to setTimeout

setTimeout(function () {

  console.log("This is an anonymous function.");

}, 1000);
```

#### Q4:What do you mean by First class function ? 

**Answer**: The following points illustrates First class function : 

- ability to pass functions inside a function as arguments
- and/or return a function (higher order function)

#### Q5:What is an iife ? 

**Answer**:An IIFE, or Immediately Invoked Function Expression, is a JavaScript function that is executed immediately after it's defined.

```javascript
(function () {

  console.log("This is an IIFE!");

})();
```

#### Q6:What is a named function expression ? 

**Answer**:Same as Function Expression but function has a name instead of being anonymous 

```javascript
var b = function xyz() {

  console.log("b called");

};

b(); //b called

xyz(); //Throws RefernceError : xyz is not defined.

/*

xyz() function is not created in global scope.

So it cant be called

*/
```

#### Q7:What will happen if we call a Named Function Expression

**Answer**:it is not created in global scope so it can't be called 

```javascript
var b = function xyz() {

  console.log("b called");

};

b(); //b called

xyz(); //Throws RefernceError : xyz is not defined.

/*

xyz() function is not created in global scope.

So it cant be called

*/
```

#### Q8:What are higher order functions ?

**Answer**:Higher-order functions are functions that operate on other functions by either taking them as arguments or returning them as results

#### Q9:Params vs arguments 

**Answer**:arguments are when we call a function , params are defined during defining the function 

```javascript
function square(num) {

  console.log(num * num);

}

square(5);

//num is the parameters , 5 is the argument
```

#### Q10:Give an example of a callback function 

**Answer**: The following code snippet illustrates a callback function

```javascript
document.addEventListener("click", function () {});
```

#### Q11:Arrow function vs regular function

**Answer**:The following function illustrates the difference between arrow function and regular function

|                   | Arrow Function                                               | Regular function                                             |
| ----------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| syntax            | uses ⇒                                                       | uses function keyword                                        |
| return            | can have implicit return                                     | does not have implicit return                                |
| arguments keyword | does not have arguments keyword                              | has arguments keyword                                        |
| This              | Iexically scoped , inherits this from surrounding lexical context | Dynamically scoped, Own this binding determined by invocation |

