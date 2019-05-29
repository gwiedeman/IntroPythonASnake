# Data

Working with ArchivesSpace data

Slides: [slides/data.html](slides/data.html)

## Getting a Resource (Collection)

* Login to an ArchivesSpace Instance
    * use port :8080
* Pick a resource (collection)
* Notice the URI

![Screenshot showing where URIs are found in the ArchivesSpace Staff interface.](img/finduri.png)

* Use `repo.resources(number)` to get a resource

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(129)
print (collection)
```

## Lists

* `myList = ["thing1", "thing2", "thing3"]`
* Can be variables or any data type
* Lists have indexes: `myList[1]`
* Lists have lengths: `len(myList)`

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

#collection = repo.resources(129)
#print (collection)

thing2 = 25
myList = ["thing1", thing2, "thing3"]

print (type(myList))
print (len(myList))
print (myList[1])
```

* Add to end of list: `myList.append("a thing")`
* Add by index: `myList.insert(1, "a thing")`
* Remove item with `myList.remove("a thing")` 
* Test with: `25 in myList`

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

#collection = repo.resources(129)
#print (collection)

thing2 = 25
myList = ["thing1", thing2, "thing3"]

myList.append(thing2)

print (len(myList))

myList.remove(25)

print (myList)

myList.insert(0, "begin")
print (myList)

print (25 in myList)
```

## Dictionaries

* Key: Value sets
* `data = {"field": "a value", "Question": "Answer"}`
* Call with key
* `data["field"]`
* Changing or adding is the same

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

#collection = repo.resources(129)
#print (collection)

data = {"field": "a value", "Question": "Answer"}

print (type(data))
print (data["Question"])
data["decription"] = "here's some info"
data["field"] = 336

print (data)
```

## Complex Data

* Dictionaries can hold lists and lists can hold dictionaries

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

#collection = repo.resources(129)
#print (collection)

data = {"field": "a value", 
    "Question": "Answer",
    "myList":  ["thing1", "thing2", "thing3"]
}

print (data["myList"][1])
```

## Using Objects

* ArchivesSnake uses objects
* Use dot syntax
* `dir(collection)` lists attributes
* `type(collection.title)` shows data type
* `collection.json()` to turns object into a dictionary

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(129)
print (collection.title)
print (dir(collection))
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(129)
print (collection.title)
print (type(collection.id_0))
print (type(collection.extents))
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(129)
print (collection.title)
print (collection.id_0)
print (collection.extents[0].number)
```

## Date Exercise

* Format collection date as EAD-style normal date
    * 1933/1998
    * 1975-08-22/1988-12-30

## Iterating with Loops

* Repeats for every item in a list
* runs indented code
* code without inded runs on completion

```python
for newVar in myList:
    print (newVar)
print ("Loop Finished")
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(129)
title = collection.title

for letter in title:
    print (letter)
    
print ("finished!!")
```

#### ArchivesSnake lets you loop though resources!!!

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

for collection in repo.resources:
    print (collection.title)
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

for collection in repo.resources:
    line = collection.id_0 + ": " + collection.title
    print (line)
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

for collection in repo.resources:
    line = collection.id_0 + ": " + collection.title
    date = collection.dates[0]
    dateString = date.begin + " - " + date.end
    
    print (line + ", " + dateString)
```
#### Using an iterator

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

count = 0
for collection in repo.resources:
    count = count + 1
    print (count)

print (str(count) + " total collections!")
```

* `count += 1` is the same as `count = count + 1`

##  If else conditionals

```python
if "a" in myString:
    print ("yes")
else:
    print ("nope")
```

```python
if "a" in myString:
    print ("yes")
elif myString == "this string":
    print ("matches exactly") 
elif myString.startswith("h"):
    print ("starts with h")    
else:
    print ("nope")
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

count = 0
for collection in repo.resources:
    count += 1
    if collection.title.lower().strip().startswith("the"):
        print (collection.title)

print (str(count) + " total collections!")
```

#### Counting types of collections

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

papers = 0
records = 0
collectionCount = 0
for collection in repo.resources:
    if "papers" in collection.title.lower():
        papers += 1
    elif "records" in collection.title.lower():
        records += 1
    elif "collection" in collection.title.lower():
        collectionCount += 1
    else:
        print (collection.title)

print (str(papers) + " papers")
print (str(records) + " records")
print (str(collectionCount) + " collections")
```

#### Collections older than 1950

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

newer = False
for collection in repo.resources:
    for date in collection.dates:
        endDate = date.end
        print (endDate)
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

newer = False
for collection in repo.resources:
    for date in collection.dates:
        endDate = date.end
        year = endDate.split("-")[0]
        if int(year) < 1950:
            print (collection.title)
```

## ArchivesSpace Trees

* Child archival objects
* Not full archival objects

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(35)
print (collection.tree.reify())
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(35)
for child in collection.tree.children:
    print (child.title)
```

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(35)
for child in collection.tree.children:
    series = child.record
    print (series)
```

#### Count the Extents

* Do the extents add up?

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(35)
for extent in collection.extents:
    print (extent.number + " " + extent.extent_type)

total = 0
for child in collection.tree.children:
    series = child.record
    print (series.title)
    for seriesExtent in series.extents:
        print ("\t" + seriesExtent.number + " " + seriesExtent.extent_type)
        total = total + float(seriesExtent.number)
        
print (total)
```



---

[Part 4: Challanges](challenges.md)