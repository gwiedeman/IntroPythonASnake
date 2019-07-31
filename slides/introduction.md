---
title: Introduction - Python and ArchivesSnake for Archivists
revealOptions:
    transition: 'fade'
---

## Python and ArchivesSnake for Archivists

### Part 1: Introduction

---

### About Me

Greg Wiedeman

University Archivist

University at Albany, SUNY

---

### Dive in Approach

* Learn Python syntax using ArchivesSpace data
* Quickest way to manuiplate data
* Get started with syntax that works, trial and error from there
* Context to know the boundaries

---

### Goals

* Create and run a Python script
* Query ArchivesSpace data with ArchivesSnake
* Understand data types
* Understand basic Python syntax
* Use Conditionals and Loops
* Edit and manipulate ArchivesSpace Data

---

### Advanced Goals

* Update or post ArchivesSpace Data
* Read local folders and text files
* Write ArchivesSpace data to local text file

---

### Things may go wrong

* Wifi issues
* Path issues
* Notebook conflicts
* ArchivesSpace instance issues

---

### About ArchivesSnake

* Python client library
* [Github page](https://github.com/archivesspace-labs/ArchivesSnake)
* Makes ArchivesSpace API easier to use
* Two Layers
    * Client layer
    * Abstraction layer
* Thanks to Dave Mayo

---

### Outline

* [Introduction](introduction.html)
    * Command Line Basics
    * Setup
        * Local install
        * Jupyter Notebooks as backup
    * First Python script
    * Jupyter Notebook basics
    
---

### Outline

* [Syntax](syntax.html)
    * Comments, white space, variables
    * Data types
    * Math with Integers
    * Get some ArchivesSpace data
    * Fun with Strings
    
---

### Outline

* [Data](data.html)
    * Getting a Resource
    * Lists
    * Dictionaries
    * Conditionals
    * Loops
    * ArchivesSpace Data
    
* [Challenges](challenges.html)
  
---

### Outline

* [Advanced](advanced.html)
    * Post Data to ArchivesSpace
    * Read local folders and text files
    * Write ArchivesSpace data to local text file
    
---

### Command Line Basics

* macOS, Linux
	* Terminal
* Windows
	* Command Prompt
	* Windows Powershell
    
---

### Command Line Basics

Your're in a folder!

![Screenshot showing the same folder in Powershell and Windows Explorer.](https://raw.githubusercontent.com/gwiedeman/IntroPythonASnake/master/img/commandLine.png)

---

### Command Line Basics

Open the folder!

* macOS
```
open .
```
* Windows
```
ii .
```

---

### Command Line Basics

* `ls` to list contents
    * Command Prompt: `dir`
* `cd <folder>` to change directory
* `cd ..` to go up one level
* `pwd` to print working directory
    * (where am I?)
    * Command Prompt: `cd`
* Up arrow for command history

---

### Pasting into Command Line

* macOS
    * Command + V
    * right-click, select paste
* Linux
    * Ctrl+shift+V
    * right-click, select paste
* Powershell or Command Prompt
    * Just right click
    * Right click on Menu, select Edit, Paste
    * Ctrl+shift+insert ?

---

### Setup

Do I have a Text Editor?

* [Notepad++](https://notepad-plus-plus.org/) (Windows only)
* [Atom](https://atom.io/)
* [Sublime Text](https://www.sublimetext.com/)
* [Visual Studio Code](https://code.visualstudio.com/)

---

### Configure Text editor (optional)

Try to change tabs to use spaces

* Notepad++
    * Settings -> Preferences... -> Language -> Check "Replace by space"
* Sublime Text 3
    * View -> Indentation -> Indent Using Spaces
* Atom
    * Default settings are fine.
    * to change: File -> Settings -> Editor -> Uncheck "Soft Tabs"

---

### Setup

Do you have Python 3?

```
python -V
> python 3.7.2

python3 -V
> python 3.6.3
```

What is your Python command?

---

### Different Python versions

* Python 2 and Python 3
* Encoding issues with Python 2
* if installed fresh, Python 3 might be `python`
* if python exists, Python 3 might be `python3`

---

### Setup

* Do I have ArchivesSnake?

```
python3 -c "import asnake"
```

* You should get no response. If you get an error, install ArchivesSnake:

```
python3 -m pip install archivessnake
```

---

### Setup ArchivesSnake

* ArchivesSpace instance
* We have to login from ArchivesSnake
* Find home directory
* create `.archivessnake.yml` file

---

### ArchivesSpace Instance

* Try in your browser
* xxxx.xxxxx.org is Public interface
* xxxx.xxxxx.org/staff is Staff interface
* xxxx.xxxxx.org/staff/api is API

---

### Find Home Directory

* Bash (macOS, Linux)
	* `echo ~`
	* Usually /home/NAME
* Powershell
	* `echo $home`
	* Usually C:\User\NAME
* Command Prompt
	* `echo %userprofile%`
	* `echo %HOMEPATH%`
	
---

### ArchivesSnake Config file

.archivessnake.yml in home directory

```
baseurl: http://localhost:8089
username: admin
password: admin
retry_with_auth: false
logging_config:
    default_config: INFO_TO_STDERR

```

* Change URL, user, password

---

### What is a Python Script?

* Its a text file
	* name ends in ".py"
	* Might start with:
    
`#!/usr/bin/env python3`

---

### How do I run a Python script?

* Command line in same directory as script
* Python command, followed by script

```python
python3 myScript.py
```

---

### Run First Script

* create `test.py`
* Command line must be in same directory

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

print (repo)
```

---

### Run First Script

```python
python3 test.py
```

---

### How to use Jupyter Notebook

* Access via IP
* Port 8888
* Sample: http://143.153.44.232:8888
* Password needed

---

### What is an API?

* REST API
* Web page for computers
* [https://archives.albany.edu/description/catalog/apap298](https://archives.albany.edu/description/catalog/apap298)
    * [https://archives.albany.edu/description/catalog/apap298**?format=json**](https://archives.albany.edu/description/catalog/apap298?format=json)
* [https://web.archive.org/web/*/https://dailygazette.com/](https://web.archive.org/web/*/https://dailygazette.com/)
    * [http://web.archive.org/cdx/search/cdx?url=https://dailygazette.com/](http://web.archive.org/cdx/search/cdx?url=https://dailygazette.com/)

---

### What is an API?

* Uses GET, POST, etc.
* Returns 200, 404, 500, etc.
* POST is how forms work
    * [Basic web form](https://library.albany.edu/archive/reference)

---

## Python and ArchivesSnake for Archivists

[Part 2: Syntax](syntax.html)
