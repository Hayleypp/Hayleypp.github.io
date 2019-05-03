

* XML 

| Meaning                                           | Example               |
| ------------------------------------------------- | --------------------- |
| select node                                       | /root/node/node       |
| select n-th node                                  | /root/node[n]         |
| select all elements that have the given attribute | /root/node/@attribute |
| get text                                          | /root/node/text()     |
| count node                                        | count(/root/node)     |



first of all, downloading document (simple.xml from w3schools.com)

1. xmllint —xpath '/breakfast_menu/food' simple.xml
2. xmllint —xpath '/breakfast_menu/food[1]' simple.xml
3. xmllint —xpath 'breakfast_menu/food[1]/price/text()' simple.xml
4. xmllint —xpath 'count(/breakfast_menu/food)' simple.xml



* xml.etree.ElementTree module: parsing and creating XML data

  

  

  1. import the data by reading from a file

  ```
  import xml.etree.ElementTree as ET
  tree = ET.parse('country_data.xml')
  root = tree.getroot()
  ```

  or directly from a string:

  ```
  root = ET.fromstring(country_data_as_string)
  ```

  As an Element, root has a tag and a dictionary of attributes

  

  



  2. Finding interesting elements

  Elements.findall() let us find only elements with a tag which are direct children of the current element.

  Element.find() finds the first child with a particular tag

  Element.get() accesses the element's attributes:

  ```python
  for country in root.findall('country'):
  	rank = country.find('rank').text
  	name = country.get('name')
  	print(name, rank)
  ```

  
  
  

  3. XPath support

  ```python
  import xml.etree.ElementTree as ET
  
  root = ET.fromstring(coutnrydata)
  
  # Nodes with name = 'Singapore' that have a 'year' child
  root.findall(".//year/..[@name='Singapore']")
  
  # All 'neighbor' nodes that are the second chld of their parent
  root.findall(".//neighbor[2]")
  ```

  







