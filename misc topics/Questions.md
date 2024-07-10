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

