## Questions on asynchronous javascript 

#### Q1:What is the call stack ?

**Answer**:The `Call Stack` manages the execution of our program. When we invoke a function, a new execution context gets created which gets pushed onto the `Call Stack`. The top-most function in the call stack is evaluated, which could in turn invoke another function, and so on.

An execution context is popped off the `Call Stack` when the function completed its execution.

#### Q2:what are web APIs

**Answer**:Web APIs are functionalities provided to the engine, but are not part of the JavaScript language itself.

#### Q3:How does javascript gets access to the web apis

**Answer**:javascript gets access to the web api’s through the global window object 

#### Q4:Give 3 examples of web APIs 

**Answer**:fetch(),setTimeOut(),DOM()

#### Q5:Where does asynchronous tasks run in javascript

**Answer**:in web apis 

#### Q6:What is a callback queue ?

**Answer**:Ready to be executed callback functions

#### Q7:What is the MicroTasks Queue ?

**Answer**:Like callback queue but for callbacks related to promises .Has priority over call back queue

#### Q8:What is the event loop ?

**Answer**:Sends callbacks from callbackqueue and microtasks queue to call stack (decides when each call backback is executed)

#### Q9:What is the order in which event loop sends tasks from the Task Queue(or Callback Queue) and the microTask Queue

**Answer**:When the `Call Stack` is empty, the `Event Loop` first processes *all* microtasks from the `Microtask Queue` before moving on to the `Task Queue`.

After completing a single task from the `Task Queue`, and the `Call Stack` is empty, the `Event Loop` effectively "starts over" by processing *all* microtasks in the `Microtask Queue` before again moving on to the next task.

![event-loop](../assets/event-loop.gif)