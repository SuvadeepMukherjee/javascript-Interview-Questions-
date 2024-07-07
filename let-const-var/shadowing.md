## Shadowing 

#### Q1: What is variable shadowing and what is illelegal shadowing  ? 

**Answer**:Variable shadowing occurs *when a variable with the same name is declared in an inner scope such as a function or block as a variable in an outer scope*, While shadowing a variable *it should not cross the boundary of the scope if it crosses the scope then it is illegal shadowing for instance we cannot shadow a let variable with a var variable declared in block scope*

#### Q2:Guess the ouput of following code snippet ? 

```javascript
var a = 100;

{

  var a = 10;

  let b = 20;

  const c = 30;

  console.log(a);

}

console.log(a);
```

**Answer**:The output  will be the follwing `10 10` 

#### Q3:Guess the output of the following code snippet ? 

```javascript
const c = 100;

function x() {

  const c = 10;

  console.log(c);

}

x();

console.log(c);
```

**Answer**:The output will be the follwing `10 100`

##### Q4:Guess the output of the follwing code snippet ? 

```javascript
var a = 100;

{

  let a = 10;

  let b = 20;

  const c = 30;

  console.log(a);

}

console.log(a);
```

**Answer**:The output will be `10 100`

#### Q5: Guess the output of the follwing code snippet ? 

```javascript
let a = 10;

{

  var a = 100;

  console.log(a);

}

console.log(a);
```

**Answer**: error , this is *illegal shadowing* 