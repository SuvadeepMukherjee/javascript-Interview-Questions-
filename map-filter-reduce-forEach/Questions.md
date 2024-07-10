## Questions on map-filter-reduce-forEach

#### Q1:const nums =[1,2,3,4] Using Map method return a new array where every element is multiplied by 3 + currentIndex

**Answer**: The output is shown below: 

```javascript
const nums = [1, 2, 3, 4];

const mappedNums = nums.map((element, index, arr) => element * 3 + index);


```

#### Q2:const nums =[1,2,3,4] Log every element to the console using the forEach Method

**Answer**:The output is shown below 

```javascript
const nums = [1, 2, 3, 4];

nums.forEach((element) => console.log(element));
```

#### Q3:Take any array and return a new array using filter method filtering only the even elements

**Answer**: The output is shown below 

```javascript
const arr = [1, 2, 3, 4];

const filterArray = arr.filter((element) => element % 2 === 0);
```

#### Q4:Given an arr=[1,2,3,4] ,return the sum of the array + 10 with the help of reduce method

**Answer**: The output of the code is shown below 

```javascript
const arr = [1, 2, 3, 4];

const sumWithInitialValue = arr.reduce(

  (accumulator, element, index, arr) => accumulator + element,

  10

);
```

#### Q5:forEach vs map 

| Feature                      | forEach                              | map                                |
| ---------------------------- | ------------------------------------ | ---------------------------------- |
| returns                      | undefined                            | returns a new array                |
| chaining other array methods | not possible as it returns undefined | possible as it returns a new array |

#### Q6:What will be logged to the console ? 

```javascript
let arr = [1, 2, 3, 4, 5];

const newArr = arr.forEach((element, index, array) => {

  console.log("Element: " + element + " index :" + index);

  return element + index;

});

console.log(newArr);
```

**Answer**: The follwing will be logged 

Element: 1 index :0 <br>

Element: 2 index :1<br>

Element: 3 index :2<br>

 Element: 4 index :3<br>

 Element: 5<br>

 index :4 undefined

#### Q7:Guess the ouput of the following code snippet ?

```javascript
let arr = [1, 2, 3, 4, 5];

const newArr = arr.map((element, index, array) => {

  console.log("Element: " + element + " index :" + index);

  return element + index;

});

console.log(newArr);
```

**Answer**: The following will be logged to the console 

Element: 1 index :0<Br> Element: 2 index :1 <BR>Element: 3 index :2<br> Element: 4 index :3 <br>Element: 5 index :4 <br>[ 1, 3, 5, 7, 9 ] 

#### Q8:Polyfill for map 

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

#### Q9:Polyfill for filter 

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

#### Q10:Polyfill for reduce 

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

```javascript
/*
Code snippet for Q11-q15
*/

let student = [

  { name: "Piyush", rollNumber: 31, marks: 80 },

  {

    name: "Jenny",

    rollNumber: 15,

    marks: 69,

  },

  {

    name: "Kaushal",

    rollNumber: 16,
    marks: 35,

  },

  {
    name: "Dilpreet",
    rollNumber: 7,

   marks: 55,

  },

];
```

#### Q11:Return only names of students 

**Answer**: The output is shown below 

```javascript
const names = student.map((element) => element.name);

console.log(names);
```

#### Q12:Return only details of those students who scored more than 60 and rollNumber greater than 15 

**Answer**: The output is shown below 

```javascript
const details = student.filter(

  (element) => element.marks > 60 && element.rollNumber > 15

);

console.log(details);
```

#### Q13:Sum of marks of all students 

**Answer**:The output is shown below 

```javascript
const sum = student.reduce(

  (accumulator, element) => accumulator + element.marks,

  0

);

console.log(sum);
```

#### Q14:Return only names of students who scored more than 60 

**Answer**:The output is shown below 

```javascript
const studentFilter = student

  .filter((element) => element.marks > 60)

  .map((element) => element.name);

console.log(studentFilter);
```

#### Q15:Return total Marks for students with marks greater than 60 after 20 marks has been added to those who scored less than 60 

**Answer**: The output is shown below 

```javascript
const students = student

  .map((element) => {

    if (element.marks < 60) {

      element.marks += 20;

    }

  return element;

  })

  .filter((element) => element.marks > 60)

  .reduce((accumulator, element) => accumulator + element.marks, 0);

console.log(students);
```

