# Tuples

## Tuples Are Like Lists

Tuples are another kind of sequence that functions much like a list  
- They have elements wich are indexed starting at 0
- Works with parenthesis

![tuples](https://i.imgur.com/Y9Es4dk.png)

## Difference with Lists : Immutable

* Tuples are immutable
  * Unlike a list, once you create a **tuple**, you **cannot alter** its contents - similar to a string
  
* You cannot sort
* You cannot append
* You cannot reverse

## A tale of Two Sequences

![](https://i.imgur.com/qBX5Ukw.png)

## Tuples Are More Efficient

Since Python does not have to built tuple structures to be modifiable,  
they are simpler and more efficient in terms of memory use and performance  
than lists.  

So in our program when we are making "temporary variables" we prefer tubles over lists.  

## Tuples and Assignment

We can also put a **tuple** on the left-hand side of an assignment statement  

We can even omit the parentheses  

        >>> (x, y) = (4, 'fred')
        >>> print(y)
        fred
        >>> (a, b) = (99, 98)
        >>> print(a)
        99
        
## Tuples and Dictionaries

The **items()** method in dictionaries returns a list of (key, value) **tuples**

        >>> d = dict()
        >>> d['csev'] = 2
        >>> d['cwen'] = 4
        >>> for (k, v) in d.items():
                print(k, v)
        ...
        csev 2
        cwen 4
        >>> tups = d.items()
        >>> print(tups)
        dict_items([('csev', 2), ('cwen', 4)])
        
## Tuples are Comparable

![](https://i.imgur.com/L99r91v.png)

## Sorting List of Tuples

![](https://i.imgur.com/cGO6dj1.png)

## Using sorted()

![](https://i.imgur.com/XvW8Hls.png)

## Sort by Values Instead of Key

![](https://i.imgur.com/g78w2JF.png)

## The top 10 most common words Code

![](https://i.imgur.com/FAEUreu.png)

## EVEN SHORTER

![](https://i.imgur.com/sARPOvf.png)


### Note

This code creates a list of tuples where each tuple is a value, key pai

     tmp = list()
     for k, v in c.items() :
         tmp.append( (v, k) )

### Assignment 10.2 

![](https://i.imgur.com/skvMLbG.png)
