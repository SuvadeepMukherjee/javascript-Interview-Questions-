## Questions on miscellenous topics

#### Q1:How can you check whther a varible is an array ?

**Answer**:Array.isArray() method determines whether the passed value is an array 

```js
const arr = [1, 2, 3];

console.log(Array.isArray(arr)); //true
```

#### Q2:Difference between null, undefined,undeclared

**Answer**:The following table illustrates the difference between null,undefined and undeclared

| Field      | Null                                        | Undefined                                | Undeclared                           |
| ---------- | ------------------------------------------- | ---------------------------------------- | ------------------------------------ |
| Defination | represents intentional absence of any value | represnts uninitialized or missing value | not declared or not in current scope |
| Type       | primitive                                   | primitive                                | N/A                                  |

#### Q3:Different ways to store data in browser ? 

**Answer**:The following table shows the different ways data can be stored in browser 

| Method          | Description                                                  |
| --------------- | ------------------------------------------------------------ |
| cookies         | Small text files stored on the client's browser.             |
| local storage   | Stores data with no expiration date.                         |
| session storage | Similar to local storage but data is cleared on tab close.   |
| IndexedDB       | Asynchronous API for storing large amounts of structured data. |

