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

