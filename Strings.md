
# Strings

* A String is a sequence of characters
* A String literal uses quotes
  - 'Hello' or "Hello"
* For String, + means "concatenate"
* When a String contains numbers, it is still a String
* We can convert numbers in a string into a number using int()

![Slicing Strings](https://i.imgur.com/qRVaDJJ.png?1)

s[0:4]  
0 -> including  
4 -> excluding  

    >>> s = 'Monthy Python'
    >>> print(s[:2])  
    Mo  
    >>> print(s[8:])  
    thon  
    >>> print(s[:])  
    Monty Python  


### String Concatenation

    >>> a = 'Hello'  
    >>> b = a + 'There'  
    >>> print(b)  
    HelloThere
    >>> c = a + ' ' + 'There'
    >>> print(c)
    Hello There
    >>> 

* When the **+** operator is applied to strings, it means "concatenation"

### Using in as a Logical Operator

    >>> fruit = 'banana'
    >>> 'n' in fruit
    True
    >>> 'm' in fruit
    False
    >>> 'nan' in fruit
    True
    >>> if 'a' in fruit:
            print('Found it!')
    Found it!
    >>>
    
### String Comparison

![Comparison](https://i.imgur.com/KfseCrA.png)

### String library

* Python has a number of string **functions** wich are in the **string library**
* These **functions** are already **built into** every string - we invoke them by appending the function to the string variable
* These **functions** do not modify the original string, instead they return a new string that has been altered.

      >>> greet = 'Hello Bob'
      >>> zap = greet.lower()
      >>> print(zap)
      hello bob
      >>> print(greet)
      Hello Bob
      >>> print('Hi There'.lower())
      hi there
      >>>
      
### Methods of a string

* The type says is a type 'str'
* class is an object-oriented term. It says that this is a thing that's of the category string
* dir says "what are strings capable of?"

![methods](https://i.imgur.com/3XjRMWD.png)

String documentation: https://docs.python.org/3/library/stdtypes.html#string-methods

### String library

![String library](https://i.imgur.com/rMUSvT3.png)

### Searching a String

* We use the **find()** function to search for a substring within another string
* **find()** finds the first occurrence of the substring
* If the substring is not found, **find()** return -1

![Searching for a String code](https://i.imgur.com/Ug7PC9t.png)

### Search and Replace

![Searche and Replace](https://i.imgur.com/KmJ7IyU.png)

### Stripping Withespace

![Stripping Withespace](https://i.imgur.com/Qe7Vjmv.png)

### Prefixes

![Prefixes](https://i.imgur.com/B7qltEG.png)

### Parsing and Extracting

![Parsing and Extracting code](https://i.imgur.com/sXWwmv0.png)
