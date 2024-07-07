## Defination Based Questions

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