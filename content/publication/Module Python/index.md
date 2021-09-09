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
</p>
<p></p><br>
<p>

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
</p>
<p></p><br>
<p>

### {{< hl >}}<b>Primitive Types</b>{{< /hl >}}<br>
`● Integer`<br>
`● Float`<br>
`● String`<br>
`● Boolean`<br>
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
</p>
<p></p><br>
<p>

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

### `❯ upper()`<br>
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
*********************************************************************************
```
</p>
<p></p><br>
<p>

### {{< hl >}}<b></b>{{< /hl >}}<br>

