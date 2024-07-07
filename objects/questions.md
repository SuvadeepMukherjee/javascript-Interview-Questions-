## Questions on objects 

#### Q1:What will be logged to the console ? 

```javascript
const user = {

  name: "Roadside Coder",

  age: 24,

};

delete user.age;

console.log(user);
```

**Answer**: The following will be logged to the console 

```javascript
{ name: 'Roadside Coder' }
```

#### Q2:What will be logged to the console ? 

```javascript
const func = (function (a) {

  delete a;

  return a;

})(5);

console.log(func);
```

**Answer**:5 , delete keyword is only used when we want to delete properties of an object(not a local variable)

#### Q3:How can we access “like this video” property ? 

```javascript
const user = {

  name: "RoadsideCoder",

  age: 24,

  "like this video": true,

};
```

**Answer**: The answer is shown in the following code snippet 

```javascript
const user = {

  name: "RoadsideCoder",

  age: 24,

  "like this video": true,

};

console.log(user["like this video"]);
```

#### Q4:How to dynamically add key -value pairs to an object , we want our user object to look like shown below with the variables dynamically ? 

```javascript
const property = "firstName";

const name = "Piyush Agarwal";

const user = {

  firstName: "Piyush Agarwal",

};
```

**Answer**:The answer is shown below 

```javascript
const property = "firstName";

const name = "Piyush Agarwal";

const user = {

[property]: name,

};

console.log(user);
```

#### Q5:what is the difference between shallow copy and deep copy 

**Answer**:

shallow copy ⇒ has got the reference to original object

deep copy ⇒ does not have reference to original object ( complete clone)

#### Q6:Show 4 different ways to deep copy an object 

**Answer**:The 4 different ways to clone an object is shown below 

```javascript
let user = {

  name: "Roadside Coder",

  age: 24,

};

const objClone1 = Object.assign({}, user);

const objClone2 = JSON.parse(JSON.stringify(user));

const objClone3 = { ...user };

const objClone4 = structuredClone(user);

user.name = "suva";

console.log(objClone1, objClone2, objClone3, objClone4);
```

#### Q7:How can we modify the array even though we are declaring it with const 

**Answer**:The value remains the same in the execution context , we are changing the object in heap 

#### Q8:Explain the different ways of creating object in javascript? Explain all the 3 ways

**Answer**: The 3 different ways to create objects are shown below 

Object Literal: This is the simplest way to create an object. You define properties and methods directly within curly braces {}

Constructor Function: You can create objects using constructor functions. Constructor functions are like regular functions, but they are called with the new keyword to create instances.

Object.create(): This method creates a new object with the specified prototype object.

```javascript
// Object.create()

let personProto = {

  greet: function () {

   console.log("Hello, my name is " + this.name);

  },

};

let person = Object.create(personProto);

person.name = "John";

person.age = 30;
```

#### Q9:Create a function multiplyByTwo(obj) that multiplies all numeric property values of the nums object by 2

```javascript
let nums = {

  a: 100,

  b: 200,

  title: "My nums",

};
```

**Answer**:The answer is given in the below code snippet 

```javascript
function multiplyByTwo(obj) {

  for (const key in obj) {

    if (typeof obj[key] === "number") {

      obj[key] *= 2;

    }

  }

}

let nums = {

  a: 100,

  b: 200,

  title: "My nums",

};

multiplyByTwo(nums);
```

#### Q10:Loop through the user object and log the keys and its values 

```javascript
const user = {

  name: "Roadside Coder",

  age: 24,

  isTotallyAwesome: true,

};
```

**Answer**: The answer is provided in the below code snippet 

```javascript
const user = {

  name: "Roadside Coder",

  age: 24,

  isTotallyAwesome: true,

};

for (const key in user) {

  console.log(`${key}:${user[key]}`);

}
```

#### Q11:Given a studentObj as as shown above write the code to iterate through studentObj and find the average age of students  i.e 25 in this case

```javascript
const studentObj = {

  yash: 26,

  vaibhav: 24,

  rajesh: 25,

};
```

**Answer**: The answer is given in below code snippet 

```javascript
const studentObj = {

  yash: 26,

  vaibhav: 24,

  rajesh: 25,

};

let length = Object.values(studentObj).length;

let sum = 0;

for (const key in studentObj) {

  sum += studentObj[key];

}

console.log(sum / length);
```

#### Q12:Given a studentObj as shown above write the code to iterate through studentObj and find the name whose age is 25 .i.e Rajesh

**Answer**: The answer is shown in the below code snippet

```javascript
const studentObj = {

  yash: 26,

  vaibhav: 24,

  rajesh: 25,

};

for (const key in studentObj) {

  if (studentObj[key] === 25) {

   console.log(key);

  }

} 
```

#### Q13:Guess the output of below code snippet 

```javascript
const obj = {

  a: "one",

  b: "two",

  a: "three",

};

console.log(obj);
```

**Answer**:The output is shown below 

```javascript
{ a: 'three', b: 'two' }
```

#### Q14:Guess the output of below code snippet 

```javascript
const a = {};

const b = { key: "b" };

const c = { key: "c" };

a[b] = 123;

a[c] = 456;

console.log(a[b]);
```

**Answer**: 456 , explanation:- In javascript when we try to use an object as a key in another object it gets converted to a string , However the default string representation of an object is “[object object]” Thus 456 will be logged to the console

#### Q15:What will be logged to the console ? 

```javascript
console.log([..."Lydia"]);
```

**Answer**:`[ 'L', 'y', 'd', 'i', 'a' ]`

#### Q16:What will be logged to the console ? 

```js
const user = { name: "Lydia", age: 21 };

const admin = { admin: true, ...user };

console.log(admin);
```

**Answer**:`{ admin: true, name: 'Lydia', age: 21 }`

#### Q17:What will be logged to the console ?

```js
let c = { greeting: "Hey" };

let d;

d = c;

c.greeting = "Hello";

console.log(d.greeting);
```

**Answer**:“Hello”

#### Q18:What will be the 2 console logs 

```js
console.log({ a: 1 } == { a: 1 });

console.log({ a: 1 } === { a: 1 });
```

**Answer**:both will log false since  JavaScript compares objects by reference, not value

#### Q19:What is JSON.stringify and JSON.parse

**Answer**:

JSON.stringify ⇒ convert object to string

JSON.parse ⇒ convert string to object

#### Q20:Applications of JSON.stringify and JSON.parse 

**Answer**:we cannot store objects in local storage because javascript will try to  convert it into string resulting in '[Object object]' so we need to convert  the object into a string before storing it in localStorage

```js
const user = {

  name: "Swapan",

  age: 67,

};

const strObj = JSON.stringify(user);

localStorage.setItem("test", strObj);

console.log(JSON.parse(localStorage.getItem("test")));
```

#### Q21:What will be logged to the console ? 

```js
const settings = {

  userName: "Piyush",

  level: 19,

  health: 50,

};

const data = JSON.stringify(settings, ["level", "health"]);

console.log(data);
```

**Answer**: The output is shown below 

{"level":19,"health":50}, It will only stringify the properties provided that is level and health 

#### Q22:How do you rename a variable in a destructuring assignment that is already declared ?

```js
let user = {

  name: "Piyush",

  age: 24,

};

const name = "Roadside Coder";

//error Cannot redeclare block-scoped variable 'name'

const { name } = user;
```

**Answer**:The solution is provided in the below code snippet 

```js
let user = {

  name: "Piyush",

  age: 24,

};

const name = "Roadside Coder";

const { name: myName } = user;

console.log(myName);
```

#### Q23:What will be logged to the console ?

```js
function getItems(fruitList, favoriteFruit, ...args) {

  return [...fruitList, ...args, favoriteFruit];

}

console.log(getItems(["banana", "apple"], "pear", "orange"));


```

**Answer**: The output is shown below 

`[ 'banana', 'apple', 'orange', 'pear' ]`