# Files

We must tell Python wich file we are going to work with and what we will be doing with the file.  

* This is done with the **open()** function
* **open()** returns a "*file handle*" - a variable used to perform operations on the file.

      - handle = open(filename, mode)
      filename: the name of the file
      mode: wheter we're going to read it or write it
      
* returns a handle use to manipulate the file
* filename is a string
* mode is optional and should be '**r**' if we are planning to read the file and '**w**' if we are going to write to the file.

### File Handle

A **file handle** open for read can be treated as a **sequence**  
of strings where each line in the file is a string in the sequence.  
  
We can use the **for** statement to iterate through a **sequence**  

Remember - a **sequence** is an ordered set.  

    xfile = open('mbox.txt')
    for cheese in xfile:
          print(cheese)
          
### Reaging the *Whole* File

We can **read** the whole file (newlines and all) int a **single string**  

    >>> fhand = open('mbox-short.txt')
    >>> inp = fhand.read()
    >>> print(len(inp))
    94626
    >>> print(inp[:20])
    From stephen.marquar
    
### Searching Through a File (fixed)

We can strip the withespace from the right-hand side of  
the string using **rstrip()** from the string library.  

The newline is considered "white space" and is **stripped**  

    fhand = open('mbox-short.txt')
    for line in fhand:
        line = line.rstrip()
        if line.startswith('From: ') :
            print(line)

    output:
    From: stephen.marquard@utc.ac.za
    From: louis@media.berkeley.edu
    From: zqian@umich.edu
    From: rjlowe@iupui.edu
    
### Skipping with Continue

We skip the lines that starts with 'From: '

     fhand = open('mbox-short.txt')
        for line in fhand:
            line = line.rstrip()
            if not line.startswith('From: ') :
                continue
            print(line)

### Using in to select lines

We can look for a string anywhere in a line as our selection criteria.  

     fhand = open('mbox-short.txt')
        for line in fhand:
            line = line.rstrip()
            if not '@uct.ac.za' in line :
                continue
            print(line)
 
output would be:  
![inSelectLinesCode](https://i.imgur.com/L19MjXG.png)
            










          
