## Python is Strongly Typed
Types are important in Python as different types have different "behaviors". For 
example, we cannot UPPERCASE and `int` type. We cannot add a string type to an integer 
type because Python doesn't automatically convert one type to another to perform such 
operations.  

In weakly typed languages like Javascript, an operation like `"100" - 1` 
yields the result `99`.  However, Python raises a `TypeError` for the same operation. 
In this example, Javascript is being "smart" and Python is apparently being "strict". 
Consider the example `"100" + 1`.  In Javascript, the result is `"1001"`.  

If types are important, then why aren't 
types explicit?  That is to say, why aren't types included when we define a variable?
This is because Python is a dynamically typed language.  This means that the type of a 
variable is determined when the program is run--not in the source.



