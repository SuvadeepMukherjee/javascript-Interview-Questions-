## Differences between let-const-var 

#### Q1:In a tabular form write down the differences between let-const-var 

**Answer**: The following table illustrates the differences between let-cont-var 

| Feature                              | let                                                        | const                                                     | var                                                          |
| ------------------------------------ | ---------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------ |
| Re-declaration within the same scope | let cannot be re-declared within the same scope            | const cannot be re-declared within the same scope         | var can be redeclared within the same scope                  |
| declaration without initialization   | can be declared without initialization                     | cannot be declared without initialization                 | can be declared without initialization                       |
| Reinitialization                     | can be reinitialized                                       | cannot be reinitialized                                   | can be reinitilaized                                         |
| Hoisting                             | TDZ, throws a error “cannot be used before initialization” | TDZ throws a error “cannot be used before initialization” | hoisted to the top of its scope (function or global) initialized with undefined by default |

