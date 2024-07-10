## Questions on event Propagation

#### Q1:What is event bubbling ?

**Answer**:Event bubbling is a process in which an event starts from the target element and then propagates upwards through the DOM hierarchy to its parent elements. For example, if a click event occurs on a button inside a div, the event first triggers on the button and then "bubbles" up to the div, then to its parent, and so on, until it reaches the root of the document.

#### Q2:What is event capturing ?

**Answer**:Event capturing is a process in which an event propagates from the outermost element (ancestor) down to the target element before it triggers any event listeners on the target itself. 

#### Q3:What is `event.stopPropagation` 

**Answer**:This method stops the event from bubbling up (or capturing down) the DOM hierarchy, preventing other event listeners on parent elements from being triggered.

#### Q4:What is `event.stopDefault`

**Answer**:This method prevents the default action associated with an event from occurring. For example, it can stop a form from submitting or a link from being followed when clicked.