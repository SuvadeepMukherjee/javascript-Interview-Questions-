## Theoretical Questions

#### Q1:What is a closure ?

**Answer**:A closure gives a function access to all the variables of its parent function even after the parent function has returned .The function keeps a reference to its outer scope , which preseves the scope chain throughout time

#### Q2:Does closure have priority over scope chain ? 

**Answer**:Yes

#### Q3:Show an example of a closure ?

**Answer**:The following code snippet shows an example of a closure 

```javascript
function x() {

  var i = 1;

  setTimeout(function () {

   console.log(i);

  }, 3000);

  console.log("Namaste Javascript");

}

x();

// Output:

// Namaste Javascript

// 1 // after waiting 3 seconds
```

#### Q4:Implement caching/memoize function 

```javascript
const clumsyProduct = (num1, num2) => {

  for (let i = 1; i < 10000000; i++) {}

  return num1 * num2;

};

const memoizedClumsyProduct = myMemoize(clumsyProduct);

console.log(memoizedClumsyProduct(9967, 9957));
```

**Answer**:The memoize function is shown below 

```javascript
const clumsyProduct = (num1, num2) => {

  for (let i = 1; i < 10000000; i++) {}

  return num1 * num2;

};

const memoizedClumsyProduct = myMemoize(clumsyProduct);

console.log(memoizedClumsyProduct(9967, 9957));

function myMemoize(fn, context) {

  let res = {};

  return function (...args) {

    let argsCache = JSON.stringify(args);

    if (!res[argsCache]) {

      res[argsCache] = fn.call(context || this, ...args);

    }

  return res[argsCache];

  };

}
```

#### Q5:Guess the output of the following code snippet 

```javascript
let count = 0;

(function printCount() {

  if (count === 0) {

    let count = 1;

   console.log(count);

  }

  console.log(count);

})();
```

**Answer**:The output will be `1 0`