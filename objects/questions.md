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

