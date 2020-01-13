# Advanced

Advanced Python and ArchiveSnake Usage
* Updating ArchivesSpace records
* `os` module
* Reading and writing to files
* Resources

Slides: [http://www.gregwiedeman.com/presentations/workshop/advanced.html](http://www.gregwiedeman.com/presentations/workshop/advanced.html)

## Updating ArchivesSpace Records

* When you edit ArchivesSnake objects, you are not editing the data in ArchivesSpace
* Need to POST updates back to ArchivesSpace
* Soon it will be easy!
    * `collection.save()`
* Now it is challenging, need to use ArchivesSnake Client layer

* Need to get and edit JSON

```python
from asnake.aspace import ASpace
from asnake.client import ASnakeClient
client = ASnakeClient()
client.authorize()

aspace = ASpace()
repo = aspace.repositories(2)

file = repo.archival_objects(520)
print (file.title)

fileJson = file.json()
fileJson["title"] = file.title.upper()
print (fileJson["title"])

update = client.post(file.uri, json=fileJson)
print (update)
```

#### Updating a Collection Note

```python
from asnake.aspace import ASpace
from asnake.client import ASnakeClient
client = ASnakeClient()
client.authorize()

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(134)
collectJson = collection.json()

for note in collectJson["notes"]:
    if note["type"] == "scopecontent":
        for subnote in note["subnotes"]:
            print (subnote)
```

```python
from asnake.aspace import ASpace
from asnake.client import ASnakeClient
client = ASnakeClient()
client.authorize()

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(134)
collectJson = collection.json()

for note in collectJson["notes"]:
    if note["type"] == "scopecontent":
        for subnote in note["subnotes"]:
            subnote["content"] = "My new Note is very, very short."
            
update = client.post(collectJson["uri"], json=collectJson)
print
```

## File Paths in Python Scripts

* Unix-style paths: `/home/username/folder`
* Windows-style paths: `C:\Users\Username\Documents`
* UNC Paths: `\\Server\folder`
* `\` is for escaping special characters

```python
unixPath = "/home/username/folder"
windowsPath = "C:\\Users\\Username\\Documents"
uncPath = "\\\\Server\\folder"
```

## Python OS Module

* Read and edit folders and files

```python
import os

startDir = "C:\\Users\\Greg"

for folder in os.listdir(startDir):

    if folder == "myFolder":
        folderPath = os.path.join(startDir, folder)
        
        for file in folderPath:
            filePath = os.path.join(folderPath, file)
            
            if os.path.isfile(filePath):
                if file.endswith(".txt"):
                    print (file)
```

## Reading Text from a File

```python
import os

textFile = "C:\\Users\\Greg\\myFile.txt"

file = open(textFile, "r")
text = file.read()

print (text)

file.close()
```

## Serialize ArchivesSpace Data

```python
import json
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

collection = repo.resources(134)
collectJson = collection.json()

myFile = "C:\\Users\\Greg\\output.json"
file = open(myFile, "w")

file.write(json.dumps(collectJson, indent=4))

file.close()
```

## Serialize ASpace Data to CSV

```python
import os
import csv
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

startDir = "C:\\Users\\Greg"
csvFile = os.path.join(startDir, "mySheet.csv")

sheet = []
for collection in repo.resources:
    row = []
    
    id = collection.id_0
    title = collection.title
    row.append(id)
    row.append(title)
    
    for date in collection.dates:
        if "end" in dir(date):
            row.append(date.begin + "/" + date.end)
        else:
            row.append(date.begin)
    sheet.append(row)
        
file = open(csvFile, "w")
writer = csv.writer(file)
writer.writerows(sheet)
file.close()
```

## Resources

* Search and use Stack Overflow answers!
* [This Repo!](https://github.com/gwiedeman/IntroPythonASnake)
* [ArchivesSnake Wiki](https://github.com/archivesspace-labs/ArchivesSnake/wiki)
    * [ArchivesSnake Getting Started Guide](https://github.com/archivesspace-labs/ArchivesSnake/wiki/Getting-Started-Guide)
    * [ArchivesSnake Commonly Used Objects](https://github.com/archivesspace-labs/ArchivesSnake/wiki/Commonly-Used-Objects)
* [ArchivesSpace API Workshop](https://github.com/archivesspace/api-training)
* [API Overview Video - Valerie Addonizio](https://www.youtube.com/watch?v=NUtuQ-LqAr4)
* Archives Data Slack: shoes-untied.slack.com
    * Ask for an invite!
* [ArchivesSpace API docs](https://archivesspace.github.io/archivesspace/api/)



---

[Part 1: Introduction](introduction.md)
[Part 2: Syntax](syntax.md)
[Part 3: Data](data.md)
[Part 4: Challenges](challenges.md)
[Part 5: Advanced](advanced.md)