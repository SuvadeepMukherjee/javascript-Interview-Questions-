## Temporal Dead Zone 

#### Q1:What is temporal Dead Zone

**Answer**: The temporal dead zone (TDZ) is a period when a variable is declared but cannot be accessed until it's initialized.

#### Q2:Guess the ouput of the following code snippet 

```javascript
let a = 5;

var b = 6;

console.log(this.b);

console.log(window.b);

console.log(window.a);

console.log(this.a);
```

**Answer**:The output will be `6 6 undefined undefined`

#### Q3:Errors in javascript 

**Answer**:The follwing table illustrates the different types of errors in javascript

| Error                                                 | Reason                                                       |
| ----------------------------------------------------- | ------------------------------------------------------------ |
| referenceError: x is not defined                      | *x was never defined/declared*                               |
| ReferenceError:cannot access a before initialization  | *Temporal Dead Zone*                                         |
| SyntaxError: Identifier 'a' has already been declared | *redeclaring a variable that is 'let' declared.*             |
| SyntaxError: Missing initializer in const declaration | *we haven't initialized or assigned value to a const declaration* |
| TypeError: Assignment to constant variable            | *we are reassigning to a const variable.*                    |

