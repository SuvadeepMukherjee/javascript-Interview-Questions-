## Questions on compose-pipe

## Q1:Write the compose function ? 

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

