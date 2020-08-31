# XML

* Type of serialization format
* Marking up data to send accross the network

Extensible Markup language  

![Example](https://i.imgur.com/Y7wJhCg.png)

Line ends does not matters.  

**Tags** indicate the beginning and ending of elements.  
**Attributes** - Keyword/value pairs on the opening tag of XML  
**Serialize/De-Serialize** - Convert data in one program into a common format that can be stored and/or transmitted  
between systems in a programming language-independent manner.  

![](https://i.imgur.com/86NqxWN.png)

## XML Schema

If a particular piece of XML meets the specification of the Schema - It "validate".  
The act of validation of an XML consist in taking a document and a Schema Contract (Wich is also an XML document).   

![](https://i.imgur.com/elp7xsT.png)

![](https://i.imgur.com/2Os1STj.png)

2002-09-31 -> UTC/GMT (commonly use)

**XSD**: is an XML Schema. Names end in .xsd.   

## Parsing XML

# library xml.etree. ET is an alias.
import xml.etree.ElementTree as ET

    # ''' or """ -> multiline String
    data = '''<person>
        <name>Chuck</name>
        <phone type='intl'>
            +1 734 303 4456
        </phone>
        <email hide="yes"/>
    </person>'''

    tree = ET.fromstring(data) # if this line succeeds, you have good XML
    print('Name:',tree.find('name').text) # Chuck
    print('Attr:',tree.find('email').get('hide')) # yes

![](https://i.imgur.com/sGl2z4f.png)

