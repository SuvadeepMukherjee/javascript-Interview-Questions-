## Hoisting 

#### Q1: What is hoisting ? 

**Answer**:Hoisting is a concept which enables us to extract values of variables and functions even before initialising/assigning value without getting error and this is happening due to the 1st phase (memory creation phase) of the Execution Context

#### Q2:In a tabular form explain the difference between function declaration,var variables ,let and const variables and function expressions and arrow , Tell whether they are hoisted and what is the initial value 

#### **Answer**:The follwing table illustrates the  differences 

|                                | Hoisted                                 | Initial value                           |
| ------------------------------ | --------------------------------------- | --------------------------------------- |
| function declaration           | Yes                                     | actual function                         |
| var variables                  | Yes                                     | Undefined                               |
| let and const variables        | No(technically yes but not in practise) | TDZ                                     |
| function expressions and arrow | depends whether we use let,const or var | depends whether we use let,const or var |

#### Q3:Guess the output of the following code snippet 

```javascript
console.log(printName);

console.log(a);

var a = 3;

var printName = (name) => {

  console.log(name);

};
```

**Answer**:The output will be `undefined undefined`

#### Q4:Guess the output of the following code snippet 

```javascript
console.log(printName);

console.log(a);

var a = 3;

var printName = function (name) {

  console.log(name);

}; 
```

**Answer**: The output will be `undefined undefined`

#### Q5:Guess the output of the following code snippet ? 

```javascript
getName();

console.log(getName);

var getName = function () {

  console.log("Namaste Javascript");

}; 
```

**Answer**: The output will be the following `Uncaught TypeError: getName is not a function` 

#### Q6:Guess the ouput of the folowing code snippet ? 

```javascript
getName();

console.log(x);

console.log(getName);

function getName() {

  console.log("Namaste Javascript");

}
```

**Answer**: The output will be `Namaste Javascript Uncaught ReferenceError: x is not defined`

#### Q7:Guess the ouput of the follwing code snippet ?

```javascript
getName();

console.log(x);

var x = 7;

function getName() {

  console.log("Namaste Javascript");

}
```

**Answer**:The output will be `Namaste Javascript undefined` 