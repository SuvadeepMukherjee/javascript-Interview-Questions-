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