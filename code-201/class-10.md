# Class 10 Reading Notes

## JS and jQuery Chapter 10 (pg450-486)
Error Handling and Debugging 

#### Order of execution
To find source of an error, helps to know how scripts are processed. <br>
order in which statements are executed can be complex <br>
some tasks cannot complete until another statement or function has been run

#### Execution contexts
- Global context - in the script but not in a function - global scope
- function context - in a function - function-level scope
- eval context - text executed like code in an internal function

#### The stack
JS interpreter processes one line of code at a time
when a statement needs data from another function, it stacks (or piles) the new function on top of the current task. 

#### Debugging workflow
Where is the problem? <br>
What exactly is the problem <br>

### Chapter 10 Summary
- If you understand execution contexts (which have 2 stages) and stacks, youre more likely to find the error in your code
- debugging is the process of finding errors. involves a process of deduction
- the console helps narrow down the area in which the error is located, so you can try to find the exact error
- JS has 7 dif types of errors and each creats its own error object, which will tell you line num and give description of the error
- if you know that you may get an error you can handle it using the try, catch, finally statements. 
