## Questions on call-apply-bind 

#### Q1:Complete the code snippet 

```js
const lufthansa = {

  airline: "Lufthansa",

  iotaCode: "LH",

  bookings: [],

  book(flightNum, name) {

    this.bookings.push({ flight: `${this.iotaCode}${flightNum}`, name });

  },

};

const euroWings = {

  airline: "EuroWings",

  iotaCode: "EW",

  bookings: [],

};

const book = lufthansa.book;

//book a eurowings flight with the following parameter

//23,'Sarah Williams 'using the call method

//book a eurowings flight with the following parameter

//46,'Suvadeep Mukherjee 'using the apply method

//book a eurowings flight with the following parameter

//56,'Archana Mukherjee'using the bind method

console.log(euroWings.bookings);
```

**Answer**:The completed code snippet is shown below 

```js
const lufthansa = {

  airline: "Lufthansa",

  iotaCode: "LH",

  bookings: [],

  book(flightNum, name) {

    this.bookings.push({ flight: `${this.iotaCode}${flightNum}`, name });

  },

};

const euroWings = {

  airline: "EuroWings",

  iotaCode: "EW",

  bookings: [],

};

const book = lufthansa.book;

//book a eurowings flight with the following parameter

//23,'Sarah Williams 'using the call method

book.call(euroWings, 23, "Sarah Williams");

//book a eurowings flight with the following parameter

//46,'Suvadeep Mukherjee 'using the apply method

const bookingArray = [46, "Suvadeep Mukherjee"];

book.apply(euroWings, bookingArray);

//book a eurowings flight with the following parameter

//56,'Archana Mukherjee'using the bind method

const bookEW = book.bind(euroWings);

bookEW(56, "Archana Mukherjee");

console.log(euroWings.bookings);
```

#### Q2:Guess the output of below code snippet 

```js
var obj = {

  val: 100,

};

function fun(a) {

  console.log(this.val + a);

}

fun.call(obj);
```

**Answer**:NaN , argument for parameter a not provided

#### Q3:What will be logged to the console 

```javascript
var obj = {

  val: 100,

};

function fun(a, b, c) {

  console.log(a);

  console.log(b);

  console.log(c);

}

fun.call(obj, [3, 4, 5]);
```

**Answer**:[ 3, 4, 5 ] undefined undefined

#### Q4:Guess the output of below code snippet 

```javascript
const person = { name: "Piyush" };

function sayHi(age) {

  return `${this.name} is ${age}`;

}

console.log(sayHi.call(person, 24));

console.log(sayHi.bind(person, 24));
```

**Answer**:

Piyush is 24 [Function: bound sayHi]

#### Q5:Guess the ouput of below code snippet 

```javascript
const age = 10;

var person = {

  name: "Piyush",

  age: 20,

  getAge: function () {

    return this.age;

  },

};

var person2 = { age: 24 };

person.getAge.call(person2);
```

**Answer**:24

#### Q6:Guess the output of below code snippet 

```javascript
var status = "cool";

setTimeout(() => {

  const status = "fine";

  const data = {

    status: "chilling",

    getStatus() {

      return this.status;

    },

  };

  console.log(data.getStatus());

  console.log(data.getStatus.call(this));

}, 0);
```

**Answer**: