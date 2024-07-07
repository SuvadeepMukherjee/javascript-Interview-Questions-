## Polyfills 

#### Q1:Polyfill for map 

**Answer**: The answer is given below 

```javascript
const arr = [1, 2, 3];

Array.prototype.myMap = function (cb) {

  let temp = [];

  for (let i = 0; i < this.length; i++) {

​    temp.push(cb(this[i], i, this));

  }

  return temp;

};

const mappedArrayProptotype = arr.myMap((element, index) => element + index);

const mappedArray = arr.map((element, index) => element + index);

console.log(mappedArrayProptotype);

console.log(mappedArray);
```

#### Q2:Polyfill for filter 

**Answer**: The polyfill for filter is shown below 

```javascript
const arr = [1, 2, 3];

Array.prototype.myFilter = function (cb) {

  let temp = [];

  for (let i = 0; i < this.length; i++) {

​    if (cb(this[i], i, this)) temp.push(this[i]);

  }

  return temp;

};

const filteredPrototype = arr.myFilter((num) => num % 2 === 0);

const filterredArray = arr.filter((num) => num % 2 === 0);

console.log(filteredPrototype);

console.log(filterredArray);
```

#### Q3:Polyfill for reduce 

**Answer**: The polyfill for reduce is shown below 

```javascript
const arr = [1, 2, 3];

Array.prototype.myReduce = function (cb, initialValue) {

  let accumulator = initialValue !== undefined ? initialValue : this[0];

  let startIndex = initialValue !== undefined ? 0 : 1;

  for (let i = startIndex; i < this.length; i++) {

  accumulator = cb.call(undefined, accumulator, this[i], i, this);

  }

  return accumulator;

};

const sum = arr.myReduce((acc, el) => acc + el, 0);

console.log(sum);
```

