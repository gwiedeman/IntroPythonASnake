# Introduction

Slides: [http://www.gregwiedeman.com/workshop/introduction.html](http://www.gregwiedeman.com/presentations/workshop/introduction.html)

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

## Setup

#### Do I have a Text Editor?

* [Notepad++](https://notepad-plus-plus.org/) (Windows only)
* [Atom](https://atom.io/)
* [Sublime Text](https://www.sublimetext.com/)
* [Visual Studio Code](https://code.visualstudio.com/)

#### Configure Text editor (optional)

Try to change tabs to use spaces

* Notepad++

    * Settings -> Preferences... -> Language -> Check "Replace by space"
* Sublime Text 3
    * View -> Indentation -> Indent Using Spaces
* Atom
    * Default settings are fine.
    * to change: File -> Settings -> Editor -> Uncheck "Soft Tabs"


### Setup Python & ArchivesSnake

* [ Setup instructions for Python 3 and ArchivesSnake](install.md)

### Confirm Python Install

`python -V`

or

`python3 -V`

### Install ArchivesSnake

```python
python3 -m pip install archivessnake
`

### Confirm ArchivesSnake Install

​```python
python3 -c "import asnake"
```

### ArchivesSpace Instances

* Try in your browser
* xxxx.xxxxx.org is Public interface
* xxxx.xxxxx.org/staff is Staff interface
* xxxx.xxxxx.org/staff/api is API

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

## First Python Script

```python
from asnake.aspace import ASpace

aspace = ASpace()
repo = aspace.repositories(2)

print (repo)
```

Run with `python3 test.py`

---

[Part 2: Syntax](syntax.md)

