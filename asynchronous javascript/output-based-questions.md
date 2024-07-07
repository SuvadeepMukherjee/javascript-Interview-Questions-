## Asynchronous js Output based Questions 

#### Q1:What will be the output of following code snippet 

```js
console.log("start");

const promise1 = new Promise((resolve, reject) => {

  console.log(1);

});

console.log("end");


```

**Answer**:start 1 end 

#### Q2:What will be the output of following code snippet 

```js
console.log("start");

const promise1 = new Promise((resolve, reject) => {

  console.log(1);

  resolve(2);

});

promise1.then((res) => {

  console.log(res);

});

console.log("end");
```

**Answer**:start 1 end 2 

#### Q3:What will be the output of following code snippet 

```js
console.log("start");

const promise1 = new Promise((resolve, reject) => {

  console.log(1);

  resolve(2);

  console.log(3);

});

promise1.then((res) => {

  console.log(res);

});

console.log("end");
```

**Answer**:start 1 3 end 2 

#### Q4:What will be the output of following code snippet 

```js
console.log("start");

const promise1 = new Promise((resolve, reject) => {

  console.log(1);

});

promise1.then((res) => {

  console.log(2);

});

console.log("end");
```

**Answer**:start 1 end 

#### Q5:What will be the output of following code snippet 

```js
console.log("start");

const fn = () =>

  new Promise((resolve, reject) => {

    console.log(1);

    resolve("success");

  });

console.log("middle");

fn().then((res) => {

  console.log(res);

});

console.log("end");
```

**Answer**:start middle 1 end success 

#### Q6:What will be the output of following code snippet 

```js
console.log("start");

Promise.resolve(1).then((res) => {

  console.log(res);

});

Promise.resolve(2).then((res) => {

  console.log(res);

});

console.log("end");
```

**Answer**:start end 1 2

#### Q7:What will be the output of following code snippet 

```js
console.log("start");

setTimeout(() => {

  console.log("setTimeout");

}, 0);

Promise.resolve().then(() => {

  console.log("resolve");

});

console.log("end");
```

**Answer**:start end resolve setTimeout

#### Q8:What will be the output of following code snippet 

```js
const promise = new Promise((resolve, reject) => {

  console.log(1);

  setTimeout(() => {

    console.log("timerStart");

    resolve("success");

    console.log("timerEnd");

  }, 0);

  console.log(2);

});

promise.then((res) => {

  console.log(res);

});

console.log(4);
```

**Answer**:1 2 4 timerStart timerEnd success

#### Q9:What will be the output of following code snippet ?

```js
const timer1 = setTimeout(() => {

  console.log("timer1");

  const promise1 = Promise.resolve().then(() => {

    console.log("promise1");

  });

}, 0);

const timer2 = setTimeout(() => {

  console.log("timer2");

}, 0);
```

**Answer**:timer1 promise1 timer2 

#### Q10:What will be the output of following code snippet ?

```js
console.log("start");

const promise1 = Promise.resolve().then(() => {

  console.log("promise1");

  const timer2 = setTimeout(() => {

    console.log("timer2");

  }, 0);

});

const timer1 = setTimeout(() => {

  console.log("timer1");

  const promise2 = Promise.resolve().then(() => {

    console.log("promise2");

  });

}, 0);

console.log("end");
```

**Answer**:start end promise1 timer1 promise2 timer2

#### Q11:What will be the output of following code snippet ?

```js
async function fun1() {

  console.log("a");

  console.log("b");

  await setTimeout(() => console.log("C"), 1000);

  await setTimeout(() => console.log("d"), 0);

  console.log("e");

}

fun1();
```

**Answer**:a b e d C , as per mdn the await operator is used to wait for a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) (only promise) and get its fulfillment value

#### Q12:What will be the output of following code snippet 

```js
async function fun1() {

  console.log("a");

  console.log("b");

  await setTimeout(() => console.log("c"), 1000);

  await setTimeout(() => console.log("d"), 0);

  console.log("e");

}

fun1();
```

**Answer**:

```js
async function fun1() {

  console.log("a");

  console.log("b");

  await new Promise((resolve, reject) => {

    setTimeout(() => {

      resolve();

      console.log("c");

    }, 1000);

  });

  await new Promise((resolve, reject) => {

    setTimeout(() => {

      resolve();

      console.log("d");

    }, 0);

  });

  console.log("e");

}

fun1();
```

#### Q13:What will be the output of following code snippet ?

```js
let a = new Promise((resolve, reject) => {

  reject({ msg: "Something went wrong" });

});

a.then((resolve) => {

  console.log(resolve);

}).catch((err) => {

  console.log(err.msg);

});
```

**Answer**:something went wrong

#### Q14:Edit the below code snippet such that it prints a first then b

```js
async function fun() {

  await new Promise((resolve, reject) => {

    setTimeout(() => {

      resolve();

      console.log("a");

    }, 2000);

  });

  console.log("b");

}

fun(); 
```

**Answer**:

```js
async function fun() {

  await new Promise((resolve, reject) => {

    setTimeout(() => {

      resolve();

      console.log("a");

    }, 2000);

  });

  console.log("b");

}

fun();
```

#### Q15:Guess the output of below code snippet 

```js
console.log("start");

setTimeout(() => {

  console.log("Inside setTimeout(macro task)");

}, 0);

Promise.resolve().then(() => {

  console.log("Inside Promise(micro-task)");

});

console.log("end");
```

**Answer**:

start end Inside Promise(micro task) Inside SetTimeout(macro task)

#### Q16:What will be logged to the console ? 

```js
blockMainThread();

console.log("start");

function blockMainThread() {

  const start = Date.now();

  while (Date.now() - start < 3000) {}

  console.log("Running");

}

console.log("end");
```

**Answer**:Running start end 

#### Q17:What will be logged to the console ?

```js
setTimeout(function a() {

  console.log("a runs");

}, 1000);

setTimeout(function b() {

  console.log("b runs");

}, 500);

setTimeout(function c() {

  console.log("c runs");

}, 0);

function d() {

  console.log("d runs");

}

d();
```

**Answer**:d runs c runs b runs a runs

#### Q18:What will be logged to the console 

```js
Promise.resolve()

  .then(function a() {

    Promise.resolve().then(function d() {

      console.log("d runs");

    });

    Promise.resolve().then(function e() {

      console.log("e rund");

    });

    throw new Error("Error occured!");

    Promise.resolve().then(function f() {

      console.log("f runs");

    });

  })

  .catch(function b() {

    console.log("b runs");

  })

  .then(function c() {

    console.log("c runs");

  });
```

**Answer**:

d runs

e runs

b runs

c runs

#### Q19:What will be logged to the console ? 

```js
Promise.resolve()

  .then(function a() {

    Promise.resolve().then(

      setTimeout(function d() {

        console.log("d runs");

      }, 0)

    );

    Promise.resolve().then(function e() {

      console.log("e rund");

    });

    throw new Error("Error occured!");

    Promise.resolve().then(function f() {

      console.log("f runs");

    });

  })

  .catch(function b() {

    console.log("b runs");

  })

  .then(function c() {

    console.log("c runs");

  });
```

**Answer**:

e rund b runs c runs d runs