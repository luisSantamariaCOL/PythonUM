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
      
### Reading Web Pages (HTML Files)

      import urllib.request, urllib.parse, urllib.error

      fhand = urllib.request.urlopen('http://www.dr-chuck.com/page1.htm')
      for line in fhand:
          print(line.decode().strip())
          
## Network Programs - Part 5

### What is Web Scraping?

* When a program or script pretends to be a browser and retrieves web pages, looks at those web pages, extracs information, and the looks at more web  pages.
* Search engines scrape web pages - we call this "spidering the web" or "web crawling"

### Why Scrape?

* You might scrape data that you can't get any other way.
* Pull data - particularly social data - who links to who?
* Get your own data back of some system that has no "export capability"
* Monitor a site for new information
* Spider the web to make a database for a search engine

### Scraping Web Pages
* There is some controversy about web page scraping and some sites are a bit snippy about ir.
* Republishing copyrighted information is not allowed
* Violating terms of service is not allowed

### BeatifulSoup Installation and using

      import urllib.request, urllib.parse, urllib.error
      from bs4 import BeautifulSoup # BeautifulSoup library

      url = input('Enter - ') # Asking for an url
      # We are going to open it, and do a read(). It all comes in to one big string
      html = urllib.request.urlopen(url).read()

      # And then we are gonna tell BeautifulSoup to parse it
      # Takes the whole file and uses this HTML parser
      soup = BeautifulSoup(html, 'html.parser')

      # Retrieve all of the anchor tags
      # We are going to go through all of the anchor tags in a document
      # Give me a list of all the anchor tags
      tags = soup('a')
      for tag in tags:
          print(tag.get('href', None)) # like a Dictionay, get the href key or None

      # OUTPUT
      # Enter - http://www.dr-chuck.com/page1.htm
      # http://www.dr-chuck.com/page2.htm

# Summary

* The TCP/IP gives us pipes / sockets between applications
* We designed application protocols to make use of these pipes
* HyperText Transfer Protocol (HTTP) is a simple yet powerful protocol
* Python has good support for sockets, HTTP, and HTML parsing

