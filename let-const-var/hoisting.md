## Hoisting 

#### Q1: What is hoisting ? 

**Answer**:Hoisting is a concept which enables us to extract values of variables and functions even before initialising/assigning value without getting error and this is happening due to the 1st phase (memory creation phase) of the Execution Context

#### Q2:In a tabular form explain the difference between function declaration,var variables ,let and const variables and function expressions and arrow , Tell whether they are hoisted and what is the initial value 

#### **Answer**:The follwing table illustrates the  differences 

|                                | Hoisted                                 | Initial value                           |
| ------------------------------ | --------------------------------------- | --------------------------------------- |
| function declaration           | Yes                                     | actual function                         |
| var variables                  | Yes                                     | Undefined                               |
| let and const variables        | No(technically yes but not in practise) | TDZ<uninitilaized>                      |
| function expressions and arrow | depends whether we use let,const or var | depends whether we use let,const or var |

