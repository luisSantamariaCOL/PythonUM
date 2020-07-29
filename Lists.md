### List

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
