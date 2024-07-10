## Questions on Classes and Constructors 

#### Q1:Convert the below code to function constructors ?

```js
class Teacher {

  constructor(name, channel, likes = 0) {

    this.name = name;

    this.channel = channel;

    this.videolikes = like;

  }

  intro() {

    return `Hey its ${this.name}! Welcome to ${this.channel} `;

  }

  like() {

    this.videolikes++;

    return `Liked this video! Current likes: ${this.videolikes}`;

  }

}
```

**Answer**:The answer is given in the following code snippet 

```js
function Teacher(name, channel, likes = 0) {

  this.name = name;

  this.channel = channel;

  this.videoLikes = likes;

}

Teacher.prototype.intro = function () {

  return `Hey its ${this.name}! Welcome to ${this.channel} `;

};

Teacher.prototype.like = function () {

  this.videolikes++;

  return `Liked this video! Current likes: ${this.videolikes}`;

};
```

#### Q2:Explain the difference between a class and an object in Javascript 

**Answer**:In JavaScript, a class is a blueprint for creating objects, while an object is an instance of a class containing data and behavior defined by the class

#### Q3:What will be logged to the console ? 

```js
class Rectangle {

  constructor(width, height) {

    this.width = width;

    this.height = height;

  }

  area() {

    return this.width * this.height;

  }

}

const square = new Rectangle(5, 5);

const rect = new Rectangle(4, 6);

square.area();

rect.area();
```

**Answer**:`25 24`

#### Q4:How does inheritance work in javascript ? 

**Answer**:inheritance in javascript is acheived using the extends keyword .It allows a subclass (child class) to inherit properties and methods from a super class(parent class)

#### Q5:What will be logged to the console ? 

```js
class Employee {

  constructor() {

    this.name = "John";

  }

  constructor(){

    this.age=30

  }

}

var employeeobj = new Employee()

console.log(employeeobj.name);
```

**Answer**:a class can only  have single constructor thus syntax error

#### Q6:Which approach is better ?

```js
//Approach 1

const jamesBond = {

  firstName: "Roadside Coder",

  lastName: "Coder",

  getFullName: function () {

    return `${this.firstName} ${this.lastName}`.trim();

  },

};

jamesBond.getFullName();

//Approach 2

class Person {

  constructor(firstName, lastName) {

    this.firstName = firstName;

    this.lastName = lastName;

  }

}

Person.prototype.getFullName = function () {

  return `${this.firstName} ${this.lastName}`.trim();

};

const bond = new Person("Roadside", "Coder");

bond.getFullName();
```

**Answer**:Second approach because method is on the prototype thus it will be more memory efficient 

#### Q7:Implement this calc.add(10).substract(5).multiply(2).divide(2).getResult()(object Chaining)

**Answer**: The following code snippet shows the result

```js
class Calculator {

  constructor() {

    this.value = 0;

  }

  add(num) {

    this.value += num;

    return this;

  }

  subtract(num) {

    this.value -= num;

    return this;

  }

  multiply(num) {

    this.value *= num;

    return this;

  }

  divide(num) {

    if (num !== 0) {

      this.value /= num;

    } else {

      throw new Error("Cannot divide by zero");

    }

    return this;

  }

  getResult() {

    return this.value;

  }

}

const calc = new Calculator();

const result = calc.add(10).subtract(5).multiply(2).divide(2).getResult();

console.log(result); // Output: 5
```

