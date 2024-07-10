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

