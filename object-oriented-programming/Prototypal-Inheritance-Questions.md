## Prototypal Inheritance Questions

#### Q1:What will be logged to the console ? 

```js
function Vehicle() {}

Vehicle.prototype.drive = function () {

  console.log("Driving a vehicle");

};

function Car() {}

Car.prototype = Object.create(Vehicle.prototype);

Car.prototype.constructor = Car;

Car.prototype.drive = function () {

  console.log("Driving a car");

};

const vehicle = new Vehicle();

const car = new Car();

vehicle.drive();

car.drive();
```

**Answer**:The output will be 

Driving a vehicle<br> Driving a car

#### Q2:Explain the difference between `__proto__` and prototype in javascript

**Answer**:The following table illustrates the difference between `__proto__` and `prototype`

|             | What it is                          | Purpose                                                      |
| ----------- | ----------------------------------- | ------------------------------------------------------------ |
| `__proto__` | a property of an object instance    | points to the prototype object from which the instance inherits |
| `prototype` | a property of constructor functions | defines the prototype for all instances created by that constructor |

#### Q3: What is `Object.setPrototypeOf` ? 

**Answer**: `Object.setPrototypeOf`  is a method in JavaScript used to set the prototype (i.e., __proto__) of a specified object to another object or null.

```javascript
var animalPrototype = {

  sound: function () {

    console.log("Making a sound.....");

  },

};

//create an object with animalPrototype as its prototype

var dog = Object.create(animalPrototype);

var cat = {

  purr: function () {

    console.log("Purring....");

  },

};

Object.setPrototypeOf(dog, cat);

dog.purr(); //purring because cat is prototype of dog
```
