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