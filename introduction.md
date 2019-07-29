# Introduction

Slides: [http://www.gregwiedeman.com/presentations/workshop/introduction.html](http://www.gregwiedeman.com/presentations/workshop/introduction.html)

## Command Line Basics

### List contents of directory

`ls`

### Change Directory

#### Bash (macOS, Linux) and Powershell

`cd`
`cd <folder>`
`cd ..`

#### Command Prompt

`dir`
`dir <folder>`
`dir ..`

### Print Working Directory (Where am I?)

#### Bash (macOS, Linux) and Powershell

`pwd`

#### Command Prompt

`cd`

### Command history

* Use the up arrow to look though old commands

### Pasting into Command Line

`echo test`

#### macOS

* Command + V
* right-click, select paste

#### Linux

* Ctrl+shift+V
* right-click, select paste

#### Powershell or Command Prompt

* Just right click
* Right click on Menu, select Edit, Paste
* Ctrl+shift+insert ?

## Setup Python & Pip

* [ Setup instructions for Python 3 and ArchivesSnake](install.md)

### Confirm Python Install

`python -V`

or

`python3 -V`

### Confirm Pip Install

`pip -V`

or

`pip3 -V`

## Install ArchivesSnake

`pip install archivessnake`

or

`pip3 install archivessnake`

### ArchivesSpace Instances

* Access via IP
* Sample: 139.256.26.11
* Port 8080 is Staff interface
	* Browser: http://139.256.26.11:8080
* Port 8081 is Public interface
	* Browser: http://139.256.26.11:8081
* Port 8089 is API
	* Browser: http://139.256.26.11:8089

### Find Home directory

#### Bash (macOS or Linux)

* `echo ~`
	* Usually /home/NAME

#### Powershell

* `echo $home`
* Usually C:\User\NAME

#### Command Prompt

* `echo %userprofile%`
* `echo %HOMEPATH%`
* Usually C:\User\NAME

### Create .archivessnake.yml in Home Directory

```yml

baseurl: http://localhost:8089
username: admin
password: admin
retry_with_auth: false
logging_config:
    default_config: INFO_TO_STDERR

```

* Change URL, user, password

## Configure Text editor

Try to change tabs to use spaces

#### Notepad++

Settings -> Preferences... -> Language -> Check "Replace by space"

#### Atom

Default settings are fine.

to change: File -> Settings -> Editor -> Uncheck "Soft Tabs"

#### Sublime Text 3

View -> Indentation -> Indent Using Spaces

## First Python Script

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

print (repo)

```

Run with `python test.py`

---

[Part 2: Syntax](syntax.md)

