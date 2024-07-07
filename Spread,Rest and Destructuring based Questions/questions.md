## Spread,Rest and Destructuring based Questions

#### What is Spread Operator and what are the use cases of Spread Operator 

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

    

​		