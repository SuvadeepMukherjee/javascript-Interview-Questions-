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

#### Q8:Implement  a shape class with an area() method .Create subclass “Circle” and “Square” that inherit from Shape and override the area() method to calculate their respective areas

**Answer**: 

```js
class Shape {

  area() {

    return 0;

  }

}

class Circle extends Shape {

  constructor(radius) {

    super();

    this.radius = radius;

  }

  area() {

    return Math.PI * this.radius * this.radius;

  }

}

class Square extends Shape {

  constructor(side) {

    super();

    this.side = side;

  }

  area() {

    return this.side * this.side;

  }

}
```

#### Q9:Create a class named 'Student' with String variable 'name' and integer variable 'roll_no'.Create a constructor through which you can assign values through objects on creation of objects. if No value is passed through object then by default name should be initialized to "john" and roll_no as 2.Create a method display to print the attributes name and roll_no

**Answer**:The following code snippet illustrates the answer

```js
class Student {

  constructor(name = "John", roll_no = 2) {

    this.name = name;

    this.roll_no = roll_no;

  }

  display() {

    console.log(

      `Students Name: ${this.name},Students Roll Number: ${this.roll_no}`

    );

  }

}

const suva = new Student("suva", 1);

const john = new Student();

suva.display();

john.display();
```

#### Q10:Write a program to create a class count_objects .It must have a method get_count which returns the number of objects created in real time

**Answer**: The follwing code snippet shows the code 

```js
class count_object {

  static i = 0;

  constructor() {

    count_object.i++;

  }

  static getCount() {

    return count_object.i;

  }

}

const obj1 = new count_object();

const obj2 = new count_object();

console.log(count_object.getCount());
```

#### Q11:Create a class Parent which has a method print() which logs to the console “this is parent class”. Create a class Child which inherits from the Parent class.The child class also has a method print . It logs to the console “this is child class” and then calls the parent class method print.Create a object suva of the child class and then call the print method of suva object

**Answer**: The followinf code snippet shows the answer:

```js
class Parent {

  print() {

    console.log("this is a parent class");

  }

}

class Child extends Parent {

  print() {

    console.log("this is a child class");

    super.print();

  }

}

const suva = new Child();

suva.print();
```

