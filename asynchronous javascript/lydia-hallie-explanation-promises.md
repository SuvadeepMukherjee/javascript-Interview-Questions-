## Promise Notes Lydia Hallie

One way of creating a promise is with the new Promise constructor which receives an executor function with resolve and reject arguments

```js
new Promise((resolve, reject) => {

  //some async stuff here

});
```

When the` Promise` constructor is invoked, a few things happen:

- **A** [**Promise Object**](https://tc39.es/ecma262/#sec-properties-of-promise-instances) **is created.**
  This **Promise Object** contains several internal slots,  including the `[[PromiseState]]`, `[[PromiseResult]]`, `[[PromiseIsHandled]]`,`[[PromiseFulfillReactions]]`, and  `[[PromiseRejectReactions]]`. 

- The `[[PromiseFulfillReactions]]` field contains **Promise Reaction**s. This is an object created by chaining a `then` handler to the Promise.  

  This **Promise Reaction** contains, among other fields, a `[[Handler]]` property that holds the callback we passed to `then`. When the promise resolves, this handler is added to the `Microtask Queue` and has access to the value with which the promise resolved. 

- 

  

- **A** [**Promise Capability record**](https://tc39.es/ecma262/#sec-promisecapability-records) **is created
  **This "encapsulates" the promise and adds some additional functionality to` resolve or reject the promise.  These are functions that `control the eventual `[[PromiseState]]` and `[[PromiseResult]]` of the promise, and kick off asyncrhounous tasks

mnemonic to remember Promise Object **"Silly Rhinos Have Funny Reactions"**.

- **S**: `PromiseState`
- **R**: `PromiseResult`
- **H**: `PromiseIsHandled`
- **F**: `PromiseFulfillReactions`
- **R**: `PromiseRejectionReasons`

------



```js
new Promise((resolve,reject)=>{
    resolve("done")
})
```

.We can `*resolve*` this Promise by calling `resolve`, which is available to us through the executor function. When we call `resolve`:

1. `[[PromiseState]]` is set to `"fulfilled"`
2. `[[PromiseResult]]` is set to the value we passed to `resolve` which is`"Done!"`in this case.

------



```js
new Promise((resolve,reject)=>{
    reject("fail")
})
```

The process is similar when calling `reject`, now the  `[[PromiseState]]` is set to `"rejected"`, and the `[[PromiseResult]]` is set to the value we passed to `reject`, which is`"Fail!"`.

------



```js
new Promise((resolve,reject)=>{
    reject("fail")
})
.then(result=>console.log(result));
```

