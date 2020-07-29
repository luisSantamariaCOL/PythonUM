## List

A list is a **collection**

* A **collection** allows us to put many values in a single "variable"
* A **collection** is nice because we can carry many values around in one convenient package.

      friends = [ 'Joseph', 'Glenn', 'Sally]
      carryon = [ 'socks', 'shirt', 'perfume']

* **List constants** are surrounded by square brackets and the elements in the list are separated by commas.  
* A list element can be any Python object - even **another list**  
* A list can be empty  

      numbers = [ 1, [5, 6], 7]
      list = []
      mixed = ['red', 24, 98.6]
      
### Lists Are Mutable

* Strings are "inmutable" - we cannot change the contents of a string - we must make a new string to make any change  
* Lists are "mutable" - we can change an element of a list using the index operator.

![mutable list](https://i.imgur.com/CkNEJyZ.png)

### How Long is a List?

* The **len()** function takes a list as a parameter and returns the number of elements in the list  
* Actually **len()** tells us the number of elementes of any set or sequence (such as a string...)  

### Using the Range Function

* The **range** function returns a list of numbers that range from zero to one less than **parameter**
* We can construct an index loop using for and an integer iterator

![Two loops](https://i.imgur.com/iQAnCXm.png)

### List can concatenate

                  a = [1, 2, 3]
                  b = [4, 5, 6]
                  c = a + b
                  print(c)
                  [1, 2, 3, 4, 5, 6]
                
### Building a List from Scratch

![building list](https://i.imgur.com/f4qQUZz.png)

### Is Something in a List?

* Python provides two operators that let you check if an item is in a list.
* These are logical operators that return True or False
* They do not modify the lsit

                  some = [1, 9, 21, 10, 16]
                  9 in some
                  True
                  15 in some
                  False
                  20 not in some
                  True
                
### List are in Order

![List in order](https://i.imgur.com/Owy4Fkw.png)

### Built-in Functions and Lists

![built-in functions](https://i.imgur.com/BOuQ2xB.png)

### Average Program with Lists

![average code](https://i.imgur.com/MBRh4wx.png)


## Lists and Strings

### split method

* Split breaks a string into parts and produces a list of strings. We think of these as words. We can **access** a particular word or loop through all the words.  

![split list](https://i.imgur.com/qPtBQ3G.png)

* When you do not specify a **delimiter**, multiple spaces are treated like one delimiter.
* You can specify what **delimiter** character to use in the **spliting**

      thing = line.split(';')
      
### Split implementation

![split implementation](https://i.imgur.com/rLw4oDw.png)

### List exercise 1

![exercise 1](https://i.imgur.com/C5Qfz1r.png)

### List exercise 2

![exercise 2](https://i.imgur.com/GLVBDl1.png)
