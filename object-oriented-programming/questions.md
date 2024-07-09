## Object Oriented Programming Questions

#### Q1:What is object oriented programming ?

**Answer**:The following are the salient points about object oriented programming :-

- object-oriented programming(oop) is a programming paradigm based on the concept of objects (paradigm ⇒ style of code , how we write and organize code)
- oop was developed with the goal of organizing code , to make it more flexible and easier to maintain(avoid spaghetti code)

#### Q2:Classes and instances in traditional oop 

**Answer**: class is like a blueprint from which we can create new objects 

![traditional-oop](../assets/tarditional-oop.png)

#### Q3:What are the 4 fundamental principles of oop ?

**Answer**:The 4 fundamental principles of oop are the following :-

- Abstraction
  - Ignoring or hiding details that dont matter , allowing us to get an overview perspective of the thing we are implementing , instead of messing with details that dont really matter to our implementaion
- Encapsulation:
  - Keeping properties and methods private inside the class so they are not accessible from outside the class .Some methods can be exposed as a public interface(API)
- Inheritance
  - making all properties and methods of a certain class available to a child class , forming a hierarchical relationship between classes
- polymorphism
  - a child class can overwrite a method it inherited from a parent class

#### Q4:oop in javascript 

**Answer**:

✅ objects are linked to a prototype object

✅ Prototypal Inheritance : The prototype contains methods (behavior) that are accessible to all objects linked to that prototype

✅ Behavior (method) is delegeted to the linked prototype object

![prototypal-inheritance](../assets/prototypal-inheritance.png)

#### Q5:What are the 3 ways of implementing prototypal inheritance in javascript ?

**Answer**:The 3 ways of implementing prototypal inheritance in js are the following

1.  constructor Functions
2. ES6 Classes
3. Object.create()

#### Q6:Create a Person Constructor function it has properties firstName and birthYear and a method calcAge , Create a object matilda from the Person Constructor with the values “matilda” and 2017 and then call the calcAge method ?  

**Answer**: The following code snippet shows the solution 

```js
function Person(firstName, birthyear) {

  this.firstName = firstName;

  this.birthyear = birthyear;

}

Person.prototype.calcAge = function () {

  console.log(2037 - this.birthyear);

};

const matilda = new Person("matilda", 2017);

matilda.calcAge();
```

#### Q7:Can arrow functions work as constructor functions ? 

**Answer**: no because they dont have this 

#### Q8:Why it is recommended to add methods on the prototype property of a constructor function instead of adding direcly in the constructor function

**Answer**:to save memory 

#### Q9:What are the steps performed when we call new Person("matilda",2017)

```js
const Person = function (firstName, birthYear) {

  this.firstName = firstName;

  this.birthYear = birthYear;

};

const matilda = new Person("matilda", 2017);
```

**Answer**: The following steps are performed

1. new {} is created
2. function is called ,this={}
3. {} linked to prototype
4. function automatically return {}

#### Q10:Draw the prototype chain 

```js
const Person = function (firstName, birthYear) {

  this.firstName = firstName;

  this.birthYear = birthYear;

};

Person.prototype.calcAge = function () {

  console.log(2037 - this.age);

};

const matilda = new Person("matilda", 2017);
```

**Answer**: The prototype chain is shown below 

![prototype-chain](../assets/prototype-chain.png)

#### Q11; What is prototypal inheritance ?

**Answer**: if a property or method cannot be found in a certain object javascript will look into its prototype

#### Q12: What is prototype chain ? 

**Answer**: Series of links between objects linked through prototypes 

#### Q13:Confirm the following : 

1. Person.prototype is prototype of matilda
2. species is not a property of matilda
3. matilda is a instance of Person

![confirm](../assets/confirm.png)

**Answer**:The answer is shown below 

```js
const Person = function (firstName, birthYear) {

  this.firstName = firstName;

  this.birthYear = birthYear;

};

Person.prototype.calcAge = function () {

  console.log(2037 - this.age);

};

Person.prototype.species = "Homo sapiens";

const matilda = new Person("matilda", 2017);

console.log(Person.prototype.isPrototypeOf(matilda));

console.log(matilda.hasOwnProperty("species"));

console.log(matilda instanceof Person);
```

#### Q14:What is at the top of the prototype chain ? 

**Answer**: `Object.prototype`

#### Q15:What does the constructor property on Person.prototype object point to ? 

```js
const Person = function (firstName, birthYear) {

  this.firstName = firstName;

  this.birthYear = birthYear;

};

Person.prototype.calcAge = function () {

  console.log(2037 - this.birthYear);

};
```

**Answer**:It points back to the constructor function