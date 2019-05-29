# Syntax

Slides: [slides/syntax.html](slides/syntax.html)

## Comments

```python

# anything on line after a hash

"""
For multi-line comments,
use three quotes.

For explanations, etc.
"""
```

### test.py

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)
```

Running with `python test.py` should now do nothing

## Print

* Sends information to the console
* `print ("Hello!")`
* `print("This works too.")`

### test.py

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

print ("Hello!")
print("This works too.")
```

## White space

### test.py

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

	print ("Hello!")
print("This works too.")
```

```
File "test.py", line 8
    print ("Hello!")
    ^
IndentationError: unexpected indent
```

## Variables

 ` myVariable1 = "some text"`

* Any alphanumeric word
* Don't start with number (0-9) or underscore (_)
* Python will remember it until the end of the script

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

message = "Hello!"

print (message)
```

#### Must assign variables first

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

message = "Hello!"

print (message)

print (message2)
```

```
Hello!
Traceback (most recent call last):
  File "test.py", line 12, in <module>
    print (message2)
NameError: name 'message2' is not defined
```

## Basic Data Types

* Strings: `"This is a string"`
* Integers: `24`
* Floats: `24.5`
* Check with `type("this is a string")`

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

### All Data types can be printed

```python
from asnake.aspace import ASpace

#aspace = ASpace()
#repo = aspace.repositories(2)

#print (repo)

myString = "This is a string of text"

myInteger = 57

stringNumber = "57"

myFloat = "23.5"

skyIsBlue = True

print (myString)
print (myInteger)
print (stringNumber)
print (myFloat)
print (skyIsBlue)
```

## Math with Integers and Floats

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

* You cannot do math with strings

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

```
1339.5
Traceback (most recent call last):
  File "test.py", line 16, in <module>
    answer2 = stringNumber + myFloat
TypeError: can only concatenate str (not "float") to str
```

## Changing Data Types

* Change to string with `str()`
* Change to integer with `int()`
* Change to float with `float()`

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

## ArchivesSpace Data!

* Get repository name as a string

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

title = repo.name

print (title)
```

## Concatenating Strings

* Use `+` to join strings together

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)
title = repo.name

print ("Repository Title: " + title)
```

* You cannot concatenate strings and integers

```
Traceback (most recent call last):
  File "test.py", line 9, in <module>
    print ("The " + title + " is the " + myCount + "th repository")
TypeError: can only concatenate str (not "int") to str
```

* Use `str()`

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)
title = repo.name

myCount = 25

print ("The " + title + " is the " + str(myCount) + "th repository")
```

## String Methods

* Get 5th character: `title[4]`
* Get 5th-8th characters: `title[4:7]`
* Length of string: `len(title)`
* Strip whitespace: `title.strip()`
* Uppercase: `title.upper()`
* Lowercase: `title.lower()`

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

* Replace characters: `title.replace("&", "and")`
* Starts with: `title.startswith()`
* Ends with: `title.endswith()`

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)
title = repo.name

changed = title.replace("&", "and")

print (title.startswith("me"))
escaped = title.replace(".", "")
print (escaped.lower())
print (escaped.lower().startswith("me"))

print (changed)
```

---

[Part 3: Data](data.md)