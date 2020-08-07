# Using Python to Access Web Data

## Network Programs - Part 3

### Representing Simple Strings
* Each character is represented by a number between 0 and 256 stored in 8 bits of memory
* We refer to "8 bits of memory as a "byte" of memory - (i.e. my disk drive contains 3 Terabytes of memory)
* The **ord()** function tells us the numeric value of a simple ASCII character

      >>> print(ord('H'))
      72
      >>> print(ord('e'))
      101
      >>> print(ord('\n'))
      10
      >>>

* In ASCII, 'Hi' < 'zzz' (All uppercase letters are less than lowercase letters)  
* In Python 3, all strings are Unicode

### Python Strings to Bytes

* When we talk to an external resource like a network socket we sends bytes, so we need to encode Python 3 strings into a given character encoding.
* When we read data from an external resource, we must decode it based on the character set so it is properly represented in Python 3 as a string.

      while True:
          data = mysock.recv(512)
          if ( len(data) < 1) :
              break
          mystring = data.decode()
          print(mystring)
          
* In an HTTP Request in Python, when we are sending data we are going to turn it into bytes with string.**encode()**
* encode() takes a string ('GET ... ') and makes it into bytes. Bytes that are properly encoded in UTF-8

![](https://i.imgur.com/86bOIWI.png)
![](https://i.imgur.com/MF6FCBa.png)

## Network Program - Part 4

### Using urllib in Python

Since HTTP is so common, we have a library that does all the socket work for us and makes web pages look like a file  

urllib1.py:  

      import urllib.request, urllib.parse, urllib.error
      
      fhand = urllib.request.urlopen('http://data.pr4e.org/romeo.txt')
      for line in fhand:
          print(line.decode.strip())


### Like a File...

urlwords.py:  

      import urllib.request, urllib.parse, urllib.error

      fhand = urllib.request.urlopen('http://data.pr4e.org/romeo.txt')

      counts = dict()
      for line in fhand:
          words = line.decode.split()
          for word in words:
              counts[word] = counts.get(word, 0) + 1
      print(counts)
      
### Reding Web Pages (HTML Files)

