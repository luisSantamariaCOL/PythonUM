
## Dictionaries

* Dictionaries in Python are the most powerful data collection
* Dictionaries allow us to do fast database-like operations in Python
* Dictionaries in Python do not mantain order

![dictionaries](https://i.imgur.com/BDWxryS.png)

### Dictionary Literals (Constants)

![Dictionary Literals](https://i.imgur.com/hVqrMfq.png)

### Dictionaries with name counts

![dictionary with name counts](https://i.imgur.com/7DOSkLa.png)
![dictionary with name counts](https://i.imgur.com/kTDmOZq.png)

### Dictionary: Counting words

![counting words code](https://i.imgur.com/13PUuql.png)

### Definite Loops and Dictionaries

![loop dictionary](https://i.imgur.com/xrzK2e6.png)

### Retrieving lists of Keys and Values

![keys and values](https://i.imgur.com/hfGTbrt.png)

### Two Iteration Variables!

![two iteration variables](https://i.imgur.com/5tsKZKr.png)

### The slide

![The slide](https://i.imgur.com/1UOnXYq.png)

### exercise 9.4

9.4 Write a program to read through the mbox-short.txt and figure out who has sent the greatest number of mail messages. The program looks for 'From ' lines and takes the second word of those lines as the person who sent the mail. The program creates a Python dictionary that maps the sender's mail address to a count of the number of times they appear in the file. After the dictionary is produced, the program reads through the dictionary using a maximum loop to find the most prolific committer.
[link](https://www.py4e.com/tools/pythonauto/?PHPSESSID=3043af9ff0be28b55b64b61de5fd05cd)

    name = input("Enter file:")
    if len(name) < 1 : name = "mbox-short.txt"
    handle = open(name)
    counts = dict()
    for line in handle:
        line = line.rstrip()
        if line.startswith('From '):
          words = line.split()
          mail = words[1]
          counts[mail] = counts.get(mail, 0) + 1
    bigvalue = None
    bigword = None
    for key,value in counts.items():
        if counts[key] is None or value > bigvalue:
            bigword = key
            bigvalue = value
    print(bigword, bigvalue)
