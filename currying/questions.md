## Currying 

#### Q1:What is currying ? 

**Answer**:Currying is a function that takes one argument at a time and returns a new function expecting the next argument .It is a conversion of function from callable as f(a,b,c) into f(a)(b)(c).They are constructed by immediately returning their inner functions simultenously

Example of currying:

```javascript
function f(a, b) {

  return "Works";

}

function fCurried(a) {

  return function (b) {

	  return "Works";

  };

}

console.log(f(1, 2));

console.log(fCurried(1)(2));
```

#### Q2:When should currying be used ? 

**Answer**:Following are the reasons why currying is good :

✅ It makes a function pure which makes it expose to less errors and side effects.

✅ It helps in avoiding the same variable again and again.

✅ It is a checking method that checks if you have all the things before you proceed.

✅ It divides one function into multiple functions so that one handles one set of responsibility.

#### Q3:Implement a function sum(1)(2)(3) which returns 6 (sum of the arguments)

```javascript
evaluate("sum")(4)(2) => 6

evaluate("multiply")(4)(2) => 8

evaluate("divide")(4)(2) => 2 
```

**Answer**:The function evaluate is shown below 

```javascript
function evaluate(string) {

  return function (a) {

    return function (b) {

      if (string === "sum") {

        return a + b;

      } else if (string === "multiply") {

        return a * b;

      } else if (string === "divide") {

        return a / b;

      }

   };

  };

}

console.log(evaluate("sum")(4)(2));
```

#### Q4:Currying vs partial application 

**Answer**: In currying the number of arguments  that a curried function has is equal to the number of nested functions in the curried function

In Partial application the number of a arguments that a partial application has is more than the number of nested functions

```javascript
function sumPartialApplication(a) {

  return (b, c) => {

    return a * b * c;

  };

}

function sumCurried(a) {

  return function (b) {

    return function (c) {

      return a + b + c;

   };

  };

}
```

