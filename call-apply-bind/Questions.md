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

