### First steps in Python

>>> x = 1 // Toma un pequeño pedazo de memoria, recuerdalo y llamalo x.  
>>> print(x) // Put something in memory and then take it back out.  
>>> x = x + 1 // Expression  
>>> print(x)  
2  
>>> exit() // exit from python, quit() also works.  

### Reserved words in python

False class return  is  finally  
None  if  for lambda  continue  
True  def from  while nonlocal  
and del global  not with  
as  elif  try or  yield  
assert  else  import  pass  
break except  in  raise  

### Sentences or Lines

x = 2 <- Assignment Statement  
x = x + 2 <- Assignment with expression  
print(x) <- Print function  

It is better to type programs into a file and tell Python to run the commands in the file.  

We add ".py" for convention, as the suffix on the end of each of these files to indicate they contain Python.

### Three of the four basic patterns of programming

* Sequential
* Reapeated
* Conditional

Code: Sequence of intructions in a programming language  

### Constants

* Their values does'nt change.  

### Python Variable Name Rules

Good: spam    eggs    spam23    _speed  
Bad:  23spam    #sign   var.12
Different:  spam    Spam    SPAM

### Operators

(+)   (-)   (*)   (/)   (**)    (%)

### Operator Precedence Rules

Parenthesis > Power > Multiplication > Addition > Left to Right  

### Type Matters

* Cannot "add 1" to a string.
* We can ask Python what type something is by using the **type(somenthing)** function

### Type Conversions

    >>> print(float(99) + 100)  
    199.0

### Integer Division

    >>> print(9/2)
    4.5

* Integer Division produces a floating point result.  

### String Conversions

* You can also use int() and float() to convert between strings and integers.

### User Input

    nam = input('who are you?')
    print('Welcome', nam)
    
* **input()** instruct Python to pause and read data.  
* The **input()** function returns a string  

### Coments in Python     ->      **#**

### Comparison Operators
