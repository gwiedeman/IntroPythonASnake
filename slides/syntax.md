---
title: Syntax - Python and ArchivesSnake for Archivists
revealOptions:
    transition: 'fade'
---

## Python and ArchivesSnake for Archivists

### Part 2: Syntax

---

### Comments


```python

# anything on line after a hash

"""
For multi-line comments,
use three quotes.

For explanations, etc.
"""

```

---

### test.py

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)
```

* `python test.py`

---

### Print

* Sends information to the console
* `print ("Hello!")`
* `print("This works too.")`

---

### test.py

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

print ("Hello!")

print("This works too.")
```

---

### White space

* Python uses white space
    * Line breaks (hit enter)
    * tabs
    * spaces
* Cleaner code
* Will not run if formatted incorrectly

---

### Variables

` myVariable1 = "some text"`

* Any alphanumeric  word
* Don't start with number (0-9) or underscore (_)
* Python will remember it until the end of the script

---

### Variables

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

message = "Hello!"

print (message)
```
---

### Variables

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

message = "Hello!"

print (message)

print (message2)
```

---

### Basic Data Types

* Strings: `"This is a string"`
* Integers: `24`
* Floats: `24.5`
* Booleans: `True` or `False`
* Check with `type("this is a string")`

---

### Basic Data Types

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

myString = "This is a string of text"

myInteger = 57

stringNumber = "57"

myFloat = 23.5

skyIsBlue = True

print (type(myString))
print (type(myInteger))
print (type(stringNumber))
print (type(myFloat))
print (type(skyIsBlue))
```

---

### Math with Operators

* Operators: `+` `-` `*` `/`

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

myInteger = 57

stringNumber = "57"

myFloat = 23.5

answer = myInteger + myFloat

print (answer)
```

---

### Math with Operators

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

myInteger = 57

stringNumber = "57"

myFloat = 23.5

answer = myInteger * myFloat
print (answer)
answer2 = stringNumber + myFloat
print (answer2)
```

---

### Changing Data Types

* Change to string with `str()`
* Change to integer with `int()`
* Change to float with `float()`

---

### Changing Data Types

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

myInteger = 57

stringNumber = "57"

myFloat = 23.5

answer = myInteger + int(stringNumber)
print (answer)
print (float(stringNumber))
```

---

### ArchivesSpace Data!

* Get repository name as a string

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

title = repo.name

print (title)
```

---

### Concatenating Strings

* Use `+` to join strings together

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)
title = repo.name

print ("Repository Title: " + title)
```

---

### Concatenating Strings

* You cannot concatenate strings and integers

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)
title = repo.name

myCount = 25

print ("The " + title + " is the " + myCount + "th repository")
```

---

### Concatenating Strings

* Use `str()`

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)
title = repo.name

myCount = 25

print ("The " + title + " is the " + str(myCount) + "th repository")
```

---

### String Methods

* Get 5th character: `title[4]`
* Get 5th-8th characters: `title[4:7]`
* Length of string: `len(title)`
* Strip whitespace: `title.strip()`
* Uppercase: `title.upper()`
* Lowercase: `title.lower()`
* Replace characters: `title.replace("&", "and")`

---

### String Methods

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)
title = repo.name

print (title[5])
print (title[5:14])
print (len(title))

extras = "   " + title + "\n\n"
print (extras)
print (extras.strip())

print (title.upper())
print (title.lower())
```

---

### String Methods

* Replace characters:
    * `title.replace("&", "and")`
* Starts with: `title.startswith()`
* Ends with: `title.endswith()`

---

### String Methods

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)
title = repo.name

changed = title.replace("&", "and")

print (title.startswith("api"))
escaped = title.replace(".", "")
print (escaped.lower())
print (escaped.lower().startswith("api"))

print (changed)
```

---

## Explore Strings

Cheatsheet:

[https://github.com/gwiedeman/IntroPythonASnake/blob/master/syntax.md](https://github.com/gwiedeman/IntroPythonASnake/blob/master/syntax.md)

---

## Python and ArchivesSnake for Archivists

[Part 3: Data](data.html)