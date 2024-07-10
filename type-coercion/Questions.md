## Questions on type coercion 

#### Q1:What is type coercion ? 

**Answer**:automatic conversion of values from one data type to another 

#### Q2:Comparision coercion 

**Answer**:Comparision operators (== and ===) perform type coercion .The == operator coerces values to the same type before comparision while === strictly compares values without coercion 

```js
console.log(10 == "10"); // true

console.log(10 === "10"); // false
```

#### Q3:what will the output (true or false) of the following be?Explain why? console.log(null === undefined) console.log(null == undefined)

**Answer**:

```js
console.log(null == undefined); // true because of type coercion

console.log(null === undefined);// false because there is no type coercion
```

#### Q4:What is the output of this console.log(0.1 + 0.2). Why is it not 0.3?

**Answer**:In binary, 0.1 and 0.2 cannot be represented precisely, just like in decimal, 1/3 cannot be represented precisely as 0.3333333... recurring. Therefore, when these numbers are added together, the result is not exactly 0.3 but a very close approximation that's slightly off due to the limitations of floating-point representation.

#### Q5:What will be the output of this console.log((0.2+ 0.3) === 0.5)

**Answer**:true

#### Q6:Difference between == and ===

**Answer**:The following table illustrates the difference 

| Feature        | ==                                      | ===                                         |
| -------------- | --------------------------------------- | ------------------------------------------- |
| Comparison     | loose equality(type coercion)           | strict equality(no type coercion)           |
| Equality Check | checks for equality after type coercion | checks for equality without type conversion |

