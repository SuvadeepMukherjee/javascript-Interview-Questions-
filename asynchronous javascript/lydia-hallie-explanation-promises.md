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

  

- **A** [**Promise Capability record**](https://tc39.es/ecma262/#sec-promisecapability-records) **is created
  **This "encapsulates" the promise and adds some additional functionality to` *resolve* or *reject* the promise.  These are functions that `control the eventual `[[PromiseState]]` and `[[PromiseResult]]` of the promise, and kick off asyncrhounous tasks

mnemonic to remember Promise Object **"Silly Rhinos Have Funny Reactions"**.

- **S**: `PromiseState`
- **R**: `PromiseResult`
- **H**: `PromiseIsHandled`
- **F**: `PromiseFulfillReactions`
- **R**: `PromiseRejectionReasons`



.