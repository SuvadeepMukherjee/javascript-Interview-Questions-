## Write the code Question on map, filter,reduce 

```javascript
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

#### Q1:Return only names of students 

**Answer**: The output is shown below 

```javascript
const names = student.map((element) => element.name);

console.log(names);
```

#### Q2:Return only details of those students who scored more than 60 and rollNumber greater than 15 

**Answer**: The output is shown below 

```javascript
const details = student.filter(

  (element) => element.marks > 60 && element.rollNumber > 15

);

console.log(details);
```

#### Q3:Sum of marks of all students 

**Answer**:The output is shown below 

```javascript
const sum = student.reduce(

  (accumulator, element) => accumulator + element.marks,

  0

);

console.log(sum);
```

#### Q4:Return only names of students who scored more than 60 

**Answer**:The output is shown below 

```javascript
const studentFilter = student

  .filter((element) => element.marks > 60)

  .map((element) => element.name);

console.log(studentFilter);
```

#### Q5:Return total Marks for students with marks greater than 60 after 20 marks has been added to those who scored less than 60 

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

