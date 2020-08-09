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

# Exercise 1

exercise: https://www.py4e.com/tools/python-data/index.php?PHPSESSID=7838753b0c44d2ac7782e43e7c87cf6a

Lee los tag span de una pagina html, extrae los numeros e imprime la suma de todos ellos.  
### Formato:  

      <tr><td>Modu</td><td><span class="comments">90</span></td></tr>  
      <tr><td>Kenzie</td><td><span class="comments">88</span></td></tr>  
      <tr><td>Hubert</td><td><span class="comments">87</span></td></tr>  

You are to find all the <span> tags in the file and pull out the numbers from the tag and sum the numbers.  
      
### output:  

$ python3 solution.py  
Enter - http://py4e-data.dr-chuck.net/comments_42.html  
Count 50  
Sum 2...  

### Code:  

      import urllib.request, urllib.parse, urllib.error
      from bs4 import BeautifulSoup
      import ssl
      import re
      # sample data: http://py4e-data.dr-chuck.net/comments_42.html
      # actual data: http://py4e-data.dr-chuck.net/comments_781706.html

      # ignore SSL certificate errors
      ctx = ssl.create_default_context()
      ctx.check_hostname = False
      ctx.verify_mode = ssl.CERT_NONE

      url = input('Enter - ')
      html = urllib.request.urlopen(url, context = ctx).read() # read the whole thing
      soup = BeautifulSoup(html, 'html.parser')

      # Retrieve all of the anchort tags
      sum = 0
      tags = soup('span') # give me the '' tag
      for tag in tags:
          line = tag.decode()
          stuff = re.findall('[0-9]+', line)
          if len(stuff) == 0 : continue
          num = int(stuff[0])
          sum += num
      print('count', len(tags))
      print('sum', sum)

# Exercise 2

Exercise 2: https://www.py4e.com/tools/python-data/index.php?PHPSESSID=a0a33e35304a7fd54fad52a504b4eea2  

###Following Links in Python

In this assignment you will write a Python program that expands on http://www.py4e.com/code3/urllinks.py. The program will use urllib to read the HTML from the data files below, extract the href= vaues from the anchor tags, scan for a tag that is in a particular position relative to the first name in the list, follow that link and repeat the process a number of times and report the last name you find.

We provide two files for this assignment. One is a sample file where we give you the name for your testing and the other is the actual data you need to process for the assignment

Sample problem: Start at http://py4e-data.dr-chuck.net/known_by_Fikret.html
Find the link at position 3 (the first name is 1). Follow that link. Repeat this process 4 times. The answer is the last name that you retrieve.
Sequence of names: Fikret Montgomery Mhairade Butchi Anayah
Last name in sequence: Anayah
Actual problem: Start at: http://py4e-data.dr-chuck.net/known_by_Leyre.html
Find the link at position 18 (the first name is 1). Follow that link. Repeat this process 7 times. The answer is the last name that you retrieve.
Hint: The first character of the name of the last page that you will load is: A

## Strategy
The web pages tweak the height between the links and hide the page after a few seconds to make it difficult for you to do the assignment without writing a Python program. But frankly with a little effort and patience you can overcome these attempts to make it a little harder to complete the assignment without writing a Python program. But that is not the point. The point is to write a clever Python program to solve the program.

## Sample output

      $ python3 solution.py
      Enter URL: http://py4e-data.dr-chuck.net/known_by_Fikret.html
      Enter count: 4
      Enter position: 3
      Retrieving: http://py4e-data.dr-chuck.net/known_by_Fikret.html
      Retrieving: http://py4e-data.dr-chuck.net/known_by_Montgomery.html
      Retrieving: http://py4e-data.dr-chuck.net/known_by_Mhairade.html
      Retrieving: http://py4e-data.dr-chuck.net/known_by_Butchi.html
      Retrieving: http://py4e-data.dr-chuck.net/known_by_Anayah.html

## Code

      # To run this, download the BeautifulSoup zip file
      # http://www.py4e.com/code3/bs4.zip
      # and unzip it in the same directory as this file

      import urllib.request, urllib.parse, urllib.error
      from bs4 import BeautifulSoup
      import ssl
      import re

      names = list()

      # Ignore SSL certificate errors
      ctx = ssl.create_default_context()
      ctx.check_hostname = False
      ctx.verify_mode = ssl.CERT_NONE


      # Asking the user to input url, count and position parameters
      url = input('Enter URL: ')
      count_str = input('Enter count: ')
      position_str = input('Enter position: ')

      count = int(count_str)
      position = int(position_str)

      # Looping through the layers of webpages 4 times
      for repeat in range(count):
          # Reading the whole fine into a single long string
          html = urllib.request.urlopen(url, context=ctx).read()

          # Creating an organised string (soup) with BeautifulSoup
          soup = BeautifulSoup(html, 'html.parser')

          # Retrieving all of the 'a' tags
          tags = soup('a')

          # Adding the name of the person at the given position to the list
          names.append(tags[position-1].contents[0])

          # Updating the URL for the next loop
          url = tags[position-1].get('href', None)

      # Printing the list with the names
      print(names)
