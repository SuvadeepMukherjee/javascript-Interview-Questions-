## Spread,Rest and Destructuring based Questions

#### Q1:What is Spread Operator and what are the use cases of Spread Operator 

**Answer**: 

- *it is used to expand or spread elements of an iterable (like an array,string or object) into individual elements*

- Use Cases of SPREAD operator➖

  - in function calls (spread an array into individual arguments)

    ```javascript
    function sum(x, y, z) {
    
      return x + y + z;
    
    }
    
    const numbers = [1, 2, 3];
    
    console.log(sum(...numbers));
    ```

  - in array literals(create a new array by spreading elements from an existing array)

    ```javascript
    const arr1 = [1, 2, 3];
    
    const arr2 = [...arr1, 4, 5, 6];
    
    console.log(arr2); //[1,2,3,4,5,6]
    ```

  - in object literals (copy properties from one object to another)

    ```javascript
    const obj1 = { a: 1, b: 2 };
    
    const obj2 = { ...obj1, c: 3 };
    
    console.log(obj2); //{ a: 1, b: 2, c: 3 }
    ```

#### Q2:What is REST operator and what are the use cases of REST operator ? 

**Answer**:

- The REST operator is used to collect multiple elements and condense them into a single array or object

- Use Cases of REST operator ➖

  - Function parameters(collect all remaining arguments into an array)

    ```javascript
    function myFunction(a, b, ...args) {
    
      console.log(a);
    
      console.log(b);
    
      console.log(args);
    
    }
    
    myFunction(1, 2, 3, 4, 5);
    ```

  - Array destructuring(collect the remaining elements into a new array)

    ```javascript
    const [first, second, ...rest] = [1, 2, 3, 4, 5];
    
    console.log(first);
    
    console.log(second);
    
    console.log(rest);
    ```

  - object destructuring(collect the remaining properties into a new object)

    ```javascript
    const { a, b, ...rest } = { a: 1, b: 2, c: 3, d: 4 };
    
    console.log(a);
    
    console.log(b);
    
    console.log(rest);
    ```

    **Important**:- There can be only one REST and it must be the last 

### Q3:What do you mean by the statement Spread Operator does a deep copy

**Answer**:Spread Operator Makes a deep copy so if we make a change in the original object(array) it will not be reflected in the new object(array) created

#### Q4:What will be obj2 ?

```javascript
const obj1 = {

  key1: "value1",

  key2: "value2",

  key3: "value3",

};

const obj2 = { ...obj1, key3: "new value", key1: "new val" };
```

**Answer**:

```javascript
{ key1: 'new val', key2: 'value2', key3: 'new value' }
```

#### Q5:What will be key1 and key3 ?

**Answer**:key1 and key3 will be `1 1000`

#### Q6:What will be logged to the console ?

```javascript
const arr1 = ['value1', 'value2'];

const [val1, val2] = arr1;

console.log(val1);

console.log(val2);
```

**Answer**:The following will be logged to the console `value1 value2`

#### Q7:What will be logged to the console ?

```javascript
const obj1 = { key1: 1, key2: 2, key3: 1000 };

let { key1, key3 } = obj1;

key1 = 20;

key3 = 123;

console.log(obj1.key1, obj1.key3);
```

**Answer**:The following will be logged to the console `1 1000`

#### Q8:What will be the output ? 

```javascript
const fn =(a,...numbers,x,y)=>{

  console.log(x,y);

}

fn(5,6,3,7)
```

**Answer**:Rest operator can only be the last in a destructuring assignment 

#### Q9:What will be logged to the console ? 

```javascript
const fn = (a, x, y, ...numbers) => {

  console.log(x, y, numbers);

};

fn(5, 6, 3, 7, 8, 9);
```

**Answer**:The following will be logged to the console `6 3 [ 7, 8, 9 ]`

#### Q10:What will be logged to the console and why ? 

```javascript
const obj1 = {

  key1: "value1",

  key2: "value2",

  key3: "value3",

};

const obj2 = { ...obj1 };

console.log(obj2 === obj1);
```

**Answer**:false because spread does a *deep copy* 