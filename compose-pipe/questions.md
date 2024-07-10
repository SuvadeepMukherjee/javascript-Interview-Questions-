## Questions on compose-pipe

#### Q1:Write the compose function ? 

```js
const addFive = (num) => {

  return num + 5;

};

const substractTwo = (num) => {

  return num - 2;

};

const multiplyFour = (num) => {

  return num * 4;

};

/*

const evaluate = compose(addFive,substractTwo,multiplyFour)

console.log(evaluate(5))=> 23 // 5*4 =20 , 20-2=18,18+5 = 23

*/
```

**Answer**:The follwing code snippet writes the compose function 

```js
function compose(...fns) {

  return function (init) {

    let result = init;

    for (let i = fns.length - 1; i >= 0; i--) {

      result = fns[i](result);

    }

    return result;

  };

}

const evaluate = compose(addFive, substractTwo, multiplyFour);

console.log(evaluate(5));
```

#### Q2:Write the pipe function 

```js
const addFive = (num) => {

  return num + 5;

};

const substractTwo = (num) => {

  return num - 2;

};

const multiplyFour = (num) => {

  return num * 4;

};

/*

const evaluate = pipe(addFive,substractTwo,multiplyFour)

console.log(evaluate(5))=>32   5+5 =10,10-2=8,8*4=32

*/
```

**Answer**:The following function shows the pipe function 

```js
function pipe(...fns) {

  return function (init) {

    let result = init;

    for (let i = 0; i < fns.length; i++) {

      result = fns[i](result);

    }

    return result;

  };

}

const evaluate = pipe(addFive, substractTwo, multiplyFour);

console.log(evaluate(5));
```

#### Q3:What is the purpose of the compose and pipe functions in JavaScript?

**Answer**:

- compose and pipe are higher-order functions used for function composition in JavaScript.
- compose takes multiple functions as arguments and returns a new function that applies these functions from right to left.
- pipe, on the other hand, applies the functions from left to right.
- Both compose and pipe are commonly used in functional programming to create new functions by combining existing ones in a specific order.