## Questions on this keyword

#### Q1:What is the window object 

**Answer**:javascript creates a window object at global space .At global space this keyword points to the window object 

#### Q2:this binding 

| this binding                                                 | What does it point to ?                                      |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| this by itself not within a function,object or whatever      | global window object                                         |
| this within a function expression, function declararation(sloppy mode) | global window object                                         |
| this within a function expression , function declaration(strict mode) | undefined                                                    |
| this of arrow function                                       | inherited from the enclosing scope where the arrow function is defined |
| this of function expression,function declaration nested within an object | this will point to immediate parent                          |
| this within a class                                          | it will point to the constructor                             |

#### Q3:Guess the output ? 

```js
console.log(this);
```

**Answer**:`Global Window object`

#### Q4:Guess the output that will be logged to the console ?

```js
function getParam() {

  console.log(this);

}

getParam();
```

**Answer**: `Global Window Object`

#### Q5:Guess the output that will be logged to the console ?

```js
"use strict";

function getParam() {

  console.log(this);

}

getParam();
```

**Answer**: `undefined`

#### Q6:Guess the output that will be logged to the console 

```js
const getParam = () => {

  console.log(this);

};

getParam();
```

**Answer**:`Global window object`

#### Q5:Guess the output that will be logged to the console ?

```js
let user = {

  name: "Piyush",

  age: 24,

  getDetails() {

	 console.log(this.name);

  },

};

user.getDetails();
```

**Answer**: Piyush

#### Q6:Guess the output that will be logged to the console ? 

```js
let user = {

  name: "Piyush",

  age: 24,

  childObj: {

    newName: "Roadside Coder",

    getDetails() {

      console.log(this.newName, "and", this.name);

   },

  },

};

user.childObj.getDetails();
```

**Answer**:Roadside coder and undefined 

#### Q7:Guess the output that will be logged to the console ?

```js
let user = {

  name: "Piyush",

  age: 24,

  getDetails: () => {

    console.log(this);

  },

};

user.getDetails();
```

**Answer**:`Global Window object`

#### Q8:Guess the output of the following code snippet ?

```js
let user = {

  name: "Piyush",

  age: 24,

  getdetails() {

    const nestedArrow = () => console.log(this.name);

    nestedArrow();

  },

};

user.getdetails();
```

**Answer**:Piyush

#### Q9:What will be logged to the console ?

```js
const user = {

  firstName: "Piyush",

  getName() {

    const firstName = "suva";

    return this.firstName;

  },

};

console.log(user.getName());
```

**Answer**:Piyush

#### Q10:What will be logged to the console ? 

```js
const user = {

  name: "Piyush",

  greet() {

    return `Hello ${this.name}`;

  },

  farewell: () => {

    return `Goodbye , ${this.name}`;

  },

};

console.log(user.greet());

console.log(user.farewell());
```

**Answer**:Hello, Piyush . Goodbye undefined

#### Q11:What will be logged to the console 

```js
let user = {

  userName: "Roadside Coder",

  rc1: () => {

    console.log("Subscibe to " + this.userName);

  },

  rc2() {

    console.log("Subscribe to  " + this.userName);

  },

};

user.rc1();

user.rc2();
```

**Answer**:Subscibe to undefined<Br> Subscribe to  Roadside Coder

#### Q12:What will be logged to the console ?

```js
const shape = {

  radius: 10,

  diameter() {

    return this.radius * 2;

  },

  perimeter: () => 2 * Math.PI * this.radius,

};

console.log(shape.diameter());

console.log(shape.perimeter());
```

**Answer**:20 NaN, arrow lexical this 