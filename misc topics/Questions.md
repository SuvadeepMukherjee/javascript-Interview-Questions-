## Questions on miscellenous topics

#### Q1:How can you check whther a varible is an array ?

**Answer**:Array.isArray() method determines whether the passed value is an array 

```js
const arr = [1, 2, 3];

console.log(Array.isArray(arr)); //true
```

#### Q2:Difference between null, undefined,undeclared

**Answer**:The following table illustrates the difference between null,undefined and undeclared

| Field      | Null                                        | Undefined                                | Undeclared                           |
| ---------- | ------------------------------------------- | ---------------------------------------- | ------------------------------------ |
| Defination | represents intentional absence of any value | represnts uninitialized or missing value | not declared or not in current scope |
| Type       | primitive                                   | primitive                                | N/A                                  |

#### Q3:Different ways to store data in browser ? 

**Answer**:The following table shows the different ways data can be stored in browser 

| Method          | Description                                                  |
| --------------- | ------------------------------------------------------------ |
| cookies         | Small text files stored on the client's browser.             |
| local storage   | Stores data with no expiration date.                         |
| session storage | Similar to local storage but data is cleared on tab close.   |
| IndexedDB       | Asynchronous API for storing large amounts of structured data. |

#### Q4:What are generator functions ?

**Answer**:normal functions follow something called a run to completion model , generator functions dont follow a run to completion model ,Invoking a generator function returns a generator object which is an iterator .We can use the yield keyword in a generator function to pause the execution 

```js
function* generatorFunction() {

  yield 1;

  console.log("First log");

  yield 2;

  console.log("Second log");

  return "Done";

}

const genObj = generatorFunction();

console.log(genObj.next());
```

The value property is equal to the value that we yielded .The done property is a boolean value which is only set to true once the generator function returned a value(not yielded)  `{ value: 1, done: false }` If we again console.log(genObj.next()) we will get `First log followed by  { value: 2, done: false }` if we again log genObj.next() we will get `second log followed by { value: 'Done', done: true }`.*We can only iterate a generator object once any further genObj.next() will result in the following object {value:”undefined” , done:true} forever , if we want to iterate it again we have to create a new generator function* 

#### Q5:What is NaN ?

**Answer**:special value that represents an unrepresentable or undefined numerical value, typically resulting from operations like dividing by zero or attempting to perform arithmetic on non-numeric values.

#### Q6:What are escape characters? Why are they used? Give code example.

**Answer**:Escape characters are special characters used in strings to represent characters that are otherwise difficult to include. They are used to include special characters like newlines

```js
let exampleString = "Hello,\nWelcome to  tutorial Hell!";

console.log(exampleString);
```

#### Q7:What is typeof an array in javascript ?

**Answer**:object

#### Q8:What are destructors ? 

**Answer**:Destructors are special member functions in C++ that are automatically called when an object goes out of scope or is explicitly deleted. They are used to release resources acquired by the object, such as memory or file handles.

#### Q9:Explain garbage collection in js.? When is a variable garbage collected?

**Answer**:Garbage collection in JavaScript is a process where the interpreter automatically frees up memory by removing unreferenced objects. Variables are garbage collected when they are no longer reachable, meaning there are no references to them in the program.

#### Q10:5 ES6 features

**Answer**: 

1. Arrow Functions: Concise syntax for function expressions.
2. let and const Declarations: Block-scoped variables.
3. Template Literals: Improved string interpolation and multiline strings.
4. Destructuring Assignment: Extract values from arrays or objects into variables.
5. Classes: Syntactical sugar for constructor functions and prototypal inheritance.

#### Q11:Pass by value and Pass by reference 

**Answer**:

Pass by Value

- When you pass a primitive type (like a number, string, or boolean) as an argument to a function, a copy of the value is passed.
- Any changes made to the parameter inside the function do not affect the original value outside the function.

Pass by Reference:

- When you pass an object (including arrays and functions) as an argument to a function, a reference to the object is passed.
- Any changes made to the object inside the function will affect the original object outside the function.