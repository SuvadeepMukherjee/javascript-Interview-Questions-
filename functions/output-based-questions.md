## Guess the ouput-based questions

#### Q1:Guess the output of the follwing code snippet 

```javascript
var x = 1;

a();

b();

console.log(x);

function a() {

  var x = 10;

  console.log(x);

}

function b() {

  var x = 100;

  console.log(x);

}
```

**Answer**:The output will be `10 100 1`

#### Q2:Guess the output of below code snippet ?

```javascript
setTimeout(() => console.log("timer1 expired"), 1000);

setTimeout(() => console.log("timer2 expired"), 0);

function x(y) {

  console.log("inside x");

  y();

}

x(function y() {

  setTimeout(() => console.log("inside y"), 0);

});
```

**Answer**:The output will be `inside x ,timer2 expired,inside y,timer1 expired  `

#### Q3:Guess the output of below code snippet 

```javascript
setTimeout(() => console.log("timer expired"), 1000);

function x(y) {

  console.log("inside x");

  y();

}

x(function y() {

  console.log("inside y");

});
```

**Answer**:The output will be `inside x ,inside y,timer expired  `

#### Q4:Add an event listener called DOMCONTENTLOADED , inside this add a call back function which consoles "DOM has loaded”

**Answer**: The code snippet is shown below 

```javascript
document.addEventListener("DOMContentLoaded",

 () => { console.log('DOM HAS LOADED') })
```

#### Q5:Guess the output of below code snippet 

```javascript
(function (x) {

  return (function (y) {

 console.log(x);

  })(2);

})(1);
```

**Answer**:1 (This happens due to closure)

#### Q6:Guess the output of below code snippet 

```javascript
for (let i = 0; i < 5; i++) {

  setTimeout(function () {

​    console.log(i);

  }, i * 1000);

}
```

**Answer**:The output will be `0 1 2 3 4 `, this happens due to closure

#### Q7:Guess the output of below code snippet 

```javascript
for (var i = 0; i < 5; i++) {

  setTimeout(function () {

   console.log(i);

  }, i * 1000);

}
```

**Answer**:The output will be `5 5 5 5 5`

#### Q8:Guess the output of below code snippet ?

```javascript
functionName();

function functionName() {

  console.log("Roadside Coder");

}
```

**Answer**: The output will be `Roadside Coder` , this happens due to closure 

#### Q9:Guess the output of below code snippet 

```javascript
var x = 21;

var fun = function () {

  console.log(x);

  var x = 20;

};

fun();
```

**Answer**: The output will be `undefined`, this happens due to hoisting and a new execution context is created for the function fun

#### Q10:Guess the output of below code snippet 

```javascript
function fn() {

  console.log(arguments);

}

const fnArr = () => {

  console.log(arguments);

};

fn(1, 2, 3);

fnArr(1, 12, 13); 
```

**Answer**:The output will be arguments object which looks like this: Arguments { 0: 1, 1: 2, 2: 3, … }, Uncaught ReferenceError: arguments is not defined