---
title: "Module Python"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin

# Author notes (optional)
author_notes: ""

date: "2021-09-08"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: ""

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["0"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: ""

abstract: ""

# Summary. An optional shortened abstract.
summary: Beside the the school we have to complete different modules in our company. In this module I start to code with the programming language python.

tags: [PiBS]

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash: Chris Ried**](https://unsplash.com/photos/ieic5Tq8YMk)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
## {{< hl >}}<b>Get Started with Python</b>{{< /hl >}}<br>
In this module I will learn how to code with Python. You will find several tasks about Python in this publication.<br>
> Write a Hello World-Program<br>
##### Input<br>
```python
# Hello World-Programm
print("Hello World")

response = "Hello Back"

print(response)
```
##### Output<br>
```
Hello World
Hello Back
```
<p></p><br>
<p></p><br>

### {{< hl >}}<b>Different types of comments</b>{{< /hl >}}<br>
In Python you have the possibility to write single-line comments or multi-line comments.<br>
```python
# I'm a single-line comment

"""
I'm
a 
multi-line
comment
"""
```
<p></p><br>
<p></p><br>

### {{< hl >}}<b>Primitive Types</b>{{< /hl >}}<br>
> Assign each primitive Type to a variable<br>
##### Input<br>
```python
#This is an integer Variable
integerVariable = 1

#This is a floating point Variable
floatVariable = 1.0

#This is a string Variable
stringVariable = "Amanoxian"

#This is a boolean Variable
booleanVariable = True

typeOfIntegerVariable = type(integerVariable)
typeOfFloatVariable = type(floatVariable)
typeOfStringVariable = type(stringVariable)
typeOfBooleanVariable = type(booleanVariable)

print(typeOfIntegerVariable)
print(typeOfFloatVariable)
print(typeOfStringVariable)
print(typeOfBooleanVariable)
```
##### Output<br>
```
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
```
<p></p><br>
<p></p><br>

### {{< hl >}}<b>String-Methods</b>{{< /hl >}}<br>
> Use different methods on a string
### `❯ capitalize()`<br>
##### Input<br>
```python
#define a string and capitalize the first letter
a = "hello world"
a = a.capitalize()

print(a)
```
##### Output<br>
```
Hello world
```
<p></p><br>

### `❯ count()`<br>
##### Input<br>
```python
#define a string variable and count the number of a specific value
brand = ["Opel", "Toyota", "Audi", "Opel", "Kia"]
tot = brand.count("Opel")
pieces = " times"

print (str(tot)+pieces)
```
##### Output<br>
```
2 times
```
<p></p><br>

### `❯ endswith()`<br>
##### Input<br>
```python
#define a string Variable and analyze the end with method endswith()
message = "Hello, my name is Python."
x = message.endswith(".")

print(x)
```
##### Output<br>
```
True
```
<p></p><br>

### `❯ find()`<br>
##### Input<br>
```python
#define a string and find a specific value with method find()
message = "Hello, my name is Python."
x = message.find("y", 15, 20)
position = "Position "

print(position+str(x))
```
##### Output<br>
```
Position 19
```
<p></p><br>

### `❯ lower()`<br>
##### Input<br>
```python
#define a string and change uppercase letters to lowercase with method lower()
message = "Hello, my name is Python."
x = message.lower()

print(x)
```
##### Output<br>
```
hello, my name is python.
```
<p></p><br>

### `❯ replace()`<br>
##### Input<br>
```python
#define a string and replace a specific value with method replace()
message = "Hello, my name is Python."
x = message.replace("Python", "Xavier")

print(x)
```
##### Output<br>
```
Hello, my name is Xavier
```
<p></p><br>

### `❯ split()`<br>
##### Input<br>
```python
#define a string and split up with method split()
message= "Hello, my name is Python."
x = message.split()

print(x)
```
##### Output<br>
```
['Hello,', 'my', 'name', 'is', 'Python.']
```
<p></p><br>

### `❯ startswith()`<br>
##### Input<br>
```python
#define a string Variable and analyze the start with method startswith()
message = "Hello, my name is Python."
x = message.startswith("Salut")

print(x)
```
##### Output<br>
```
False
```
<p></p><br>

### `❯ strip()`<br>
##### Input<br>
```python
#define a string and insert a strip with method strip()
dish = "spaghetti code"
x = dish.strip()

print("Of all dishes", x, "is my favorite")
```
##### Output<br>
```
Of all dishes spaghetti code is my favorite.
```
<p></p><br>

### `❯ upper()`
##### Input<br>
```python
#define a string and change lowercase letters to uppercase with method upper()
dish = "spaghetti carbonara"
x = dish.upper()

print(x)
```
##### Output<br>
```
SPAGHETTI CARBONARA
```
<p></p><br>
<p></p><br>

### {{< hl >}}<b>Non-Primitive Types</b>{{< /hl >}}<br>
### Lists<br>
> ● Implement a List<br>
● The list should contain: an Integer, a String and a nested list<br>
● Make a second list and merge both.<br>
##### Input<br>
```python
#define two lists and merge them together
firstList = [1, "Python", [2, "I'm a nested list"]]
secondList = [3, "Keyboard", 3.1]

print(firstList+secondList)
```
##### Output<br>
```
[1, 'Python', [2, "I'm a nested list"], 3, 'Keyboard', 3.1]
```
<p></p><br>

### Arrays<br>
> ● Make two numpy-Arrays with numbers.<br>
● Sum those arrays together.<br>
##### Input<br>
```python
#define two numpy arrays and sum those together
numpy1 = [1, 2, 3, 4, 5]
numpy2 = [5, 4, 3, 2, 1]

print(sum(numpy1 + numpy2))
```
##### Output<br>
```
30
```
<p></p><br>

### List- & Array-Methods<br>
### `❯ append()`<br>
##### Input<br>
```python
#define a list and append an element with append()
elements = [1, "Python"]
elements.append(2)

print(elements)
```
##### Output<br>
```
[1, 'Python', 2]
```
<p></p><br>

### `❯ clear()`<br>
##### Input<br>
```python
#define a list and clear all eith method clear()
fruits = ["strawberry", "apple", "orange"]

fruits.clear()

print(fruits)
```
##### Output<br>
```
[]
```
<p></p><br>

### `❯ copy()`<br>
##### Input<br>
```python
#define a list and copy the elements in an other var with method copy()
fruits = ["strawbery", "apple", "orange"]

a = fruits.copy()

print(a)
```
##### Output<br>
```
['strawbery', 'apple', 'orange']
```
<p></p><br>

### `❯ count()`<br>
##### Input<br>
```python
#define a list and count a specific element with count()
fruits = ["orange" , "lime", "orange", "apple", "orange"]
pieces = " times"

a = fruits.count("orange")

print (str(a)+pieces)
```
##### Output<br>
```
3 times
```
<p></p><br>

### `❯ extend()`<br>
##### Input<br>
```python
#define a list an extend with an other list with method extend()
fruits = ["orange" , "lime", "orange", "apple", "orange"]
otherFruits = ["papaya", "melon"]

fruits.extend(otherFruits)

print (fruits)
```
##### Output<br>
```
['orange', 'lime', 'orange', 'apple', 'orange', 'papaya', 'melon']
```
<p></p><br>

### `❯ index()`<br>
##### Input<br>
```python
#define a list and find the index of a specific element with method index()
fruits = ["orange" , "lime", "orange", "apple", "orange"]
c = fruits.index("apple")
position = "Position "

print (position+str(c))
```
##### Output<br>
```
Position 3
```
<p></p><br>

### `❯ insert()`<br>
##### Input<br>
```python
#define a list and insert an element with method insert()
fruits = ["orange" , "lime", "orange", "apple", "orange"]
fruits.insert(0, "apple")

print (fruits)
```
##### Output<br>
```
['apple', 'orange', 'lime', 'orange', 'apple', 'orange']
```
<p></p><br>

### `❯ pop()`<br>
##### Input<br>
```python
#define a list and delete a specific element with method pop()
fruits = ["orange" , "lime"]
fruits.pop(0)

print (fruits)
```
##### Output<br>
```
['lime']
```
<p></p><br>

### `❯ remove()`<br>
##### Input<br>
```python
#define a list and remove an element with method remove()
fruits = ["orange" , "lime"]
fruits.remove("lime")

print (fruits)
```
##### Output<br>
```
['orange']
```
<p></p><br>

### `❯ reverse()`<br>
##### Input<br>
```python
#define a list and reverse the order with method reverse()
fruits = ["orange" , "lime"]
fruits.reverse()

print (fruits)
```
##### Output<br>
```
['lime', 'orange']
```
<p></p><br>

### `❯ sort()`<br>
##### Input<br>
```python
#define a list and sort alphabetically with method sort()
brands = ['Mercedes', 'Jeep', 'Audi','Kia']
brands.sort()

print(brands)
```
##### Output<br>
```
['Audi', 'Jeep', 'Kia', 'Mercedes']
```
<p></p><br>
<p></p><br>

### Tuples<br>
> ● Implement a Tuple with 3 elements<br>
● Change the tuple to a 4 elements structure. Add a 4th element.<br>
● Join two Tuples.<br>
● Explain a case where tuples are better than lists as a comment or demonstrate with an example<br>
● Use all existing methods and demonstrate the usage. Explain the different parameters if they have params.<br>
##### Input<br>
```python
#define a tuple with 3 elements
thisTuple = ("lime", "orange", "banana")

print(thisTuple)
```
##### Output<br>
```
('lime', 'orange', 'banana')
```
<p></p><br>
<p></p><br>
{{% callout warning %}}
You can't insert new elements in created tuples because they have an immutable property. But you have the possibility to join serveral tuples in a new tuple. See below 🠗
{{% /callout %}}<br>

##### Input<br>
```python
#define serveral tuples and join them
thisTuple = ("lime", "orange", "banana")
nextTuple = ("papaya", "apple")

joinTuple = thisTuple + nextTuple

print(joinTuple)
```
##### Output<br>
```
('lime', 'orange', 'banana', 'papaya', 'apple')
```
<p></p><br>
<p></p><br>

### Tuple-Methods<br>
### `❯ count()`<br>
##### Input<br>
```python
#define a tuple and count a specific element with method count()
anothertuple = (2, 2, 2, 2, 3, 4, 5)

u = anothertuple.count(2)
times = " times"

print(str(u)+times)
```
##### Output<br>
```
4 times
```
<p></p><br>

### `❯ index()`<br>
##### Input<br>
```python
#define a tuple and find the index of a specific element with method index()
fruits = ("orange" , "lime", "orange", "apple", "orange")
c = fruits.index("apple")
position = "Position "

print (position+str(c))

```
##### Output<br>
```
Position 3
```
Whenever, we need to make sure that the data remains unchanged and write protected, then a tuple is the best option in Python.<br>
<p></p><br>
<p></p><br>

### Sets<br>
> ● Implement a Set with 3 elements<br>
● Add a duplicate value and then print the content. Explain what happens.<br>
● Join two sets into one with .union()<br>
● Explain a case where sets are better than lists as a comment or demonstrate with an example<br>
● Use all existing methods and demonstrate the usage. Explain the different parameters if they have params.<br>
##### Input<br>
```python
# 1. define a set with 3 elements + one similar
# 2. Join two sets into one with .union()

thisSet = {"lime", "lime", "orange", "banana"}
nextSet = {"hello", "I'm", "unordered"}

unionSet = thisSet.union(nextSet)

print(thisSet)
print(unionSet)
```
##### Output<br>
```
{'lime', 'orange', 'banana'}
{'unordered', 'banana', 'hello', "I'm", 'lime', 'orange'}
```
Sets cannot contain duplicates, and they will simply disappear. That's why we see the element "lime" only one time in the printout.
Processing a set is faster than processing a list, because each element can only occur once. This allows us to use the hash function.<br>
<p></p><br>
<p></p><br>

### Set-Methods<br>
### `❯ All methods`<br>
##### Input<br>
```python
#define a set and add an element with method add()
tuple1 = {"mouse", "rat", "cat"}
tuple1.add("dog")

print(tuple1)


#define a set and then clear it with method clear()
tuple1 = {"mouse", "rat", "cat"}
tuple1.clear()

print(tuple1)


#define a set and copy the elements in an other var with method copy()
tuple1 = {"mouse", "rat", "cat"}
tuple1copy = tuple1.copy()

print(tuple1copy)


#define two sets and show up the differences between them with method difference()
a = {"Apple", "Strawberry", "Lime"}
b = {"Apple", "Microsoft", "Google"}
c = a.difference(b)

print(c)


#define two sets and show up the differences + clear the similar elements
#with method difference_update()
a = {"Apple", "Strawberry", "Lime"}
b = {"Apple", "Microsoft", "Google"}
a.difference_update(b)

print(a)


#define a set and clear an element with method .discard()
a = {"hello", "my", "name", "is", "Python"}
a.discard("Python")

print(a)

#define two sets and show up the similar elements with method intersection()
a = {"Apple", "Strawberry", "Lime"}
b = {"Apple", "Microsoft", "Google"}
c = a.intersection(b)

print(c)


#define two sets and remove elements in which are not present in both sets
#method intersection_update()
a = {"Apple", "Banana", "Cherry"}
b = {"Google", "Microsoft", "Apple"}
a.intersection_update(b)

print(a)


#define two sets and test if there are similar elements in the two sets or not
#method isthisjoint()
x = {"cat", "fish", "dog"}
y = {"instagram", "whatsapp", "pycharm"}
z = x.isdisjoint(y)

print(z)


#define two sets and check if both sets contain the similar elements
#method issubset()
a = {1, 2, 3}
b = {4, 5, 6, 3, 2, 0}
c = a.issubset(b) 

print(c)


#define two sets and check if all items from the second set are present
#in the first set use the method issuperset()
a = {1, 2, 3, 4, 5, 6}
b = {3, 2, 1}
c = a.issuperset(b)

print(c)


#define a set and remove a random element with method pop()
d = {"Hello", "This", "Is", "Very", "Satisfying"}
d.pop()

print(d)


#define a set and remove a specific element with method remove()
d = {"Hello", "This", "Is", "Very", "Satisfying"}
d.remove("Is")

print(d)


#define two sets and show up the elements which are not present in both sets
#method symmetric_difference
a = {1, 2, 3, 4, 5, 6}
b = {3, 2, 1, 7, 8, 9, 10}
c = a.symmetric_difference(b)

print(c)


#define two sets and remove from the first set all elements which are present in both sets
#and add the remaining elements from the second set with method symmetric_difference_update
a = {1, 2, 3, 4, 5, 6}
b = {3, 2, 1, 7, 8, 9, 10}
a.symmetric_difference_update(b)

print(a)


#define two sets and create an union of them with method union()
brands = {"DC", "Nike", "Puma"}
things = {"bicycle", "car", "helmet"}

mixture = brands.union(things)

print(mixture)


#define two sets and update the first set with the elements from the second set
#method update()
brandsmixedwiththings = {"DC", "Nike", "Puma"}
things = {"bicycle", "car", "helmet", "DC", "Nike", "Puma"}
brandsmixedwiththings.update(things)

print(brandsmixedwiththings)

```
##### Output<br>
```
{'mouse', 'rat', 'dog', 'cat'}
set()
{'mouse', 'rat', 'cat'}
{'Strawberry', 'Lime'}
{'Strawberry', 'Lime'}
{'hello', 'name', 'my', 'is'}
{'Apple'}
{'Apple'}
True
False
True
{'This', 'Satisfying', 'Very', 'Hello'}
{'This', 'Satisfying', 'Very', 'Hello'}
{4, 5, 6, 7, 8, 9, 10}
{4, 5, 6, 7, 8, 9, 10}
{'Puma', 'Nike', 'car', 'bicycle', 'helmet', 'DC'}
{'Nike', 'bicycle', 'car', 'Puma', 'helmet', 'DC'}
```
<p></p><br>
