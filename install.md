# Installing Python on your local machine

Instructions on how to install Python and make sure its in your PATH so you can run scripts.

## Objectives

* Have `python -V` or `python3 -V` return a `3.x.x` version of Python greater than 3.4.0
* Successfully install ArchivesSnake
* Install a Text Editor

## Table of Contents
1. [Installing Python](#installing-python)
   * [Do I already have Python 3?](#do-i-already-have-python-3)
   * [Installing Python 3 on Windows](#windows-machines)
   * [Installing Python 3 on macOS](#macos-machines)
     * [Option 1: Using the Terminal](#option-1-using-the-terminal)
     * [Option 2: Using the Installer](#option-2-using-the-installer)
   * [Installing Python 3 on Linux](#linux-machines)
   * [Check Your Python 3 Command](#check-your-python-command)
2. [Installing ArchivesSnake](#installing-archivessnake)
3. [Installing a Text Editor](#installing-a-text-editor)

## Installing Python

### Do I already have Python 3?

There are two main versions of Python, Python 2 and Python 3. We will be using Python 3, and there are very few reasons to still use Python 2.

If you are using macOS or a Linux distribution, you probably already have a version of Python installed, but it might only be Python 2. If you are using Windows, chances are that you don't have Python installed unless you installed it yourself.

##### Check my Python Install

1. To check you Python install open a command line terminal. 

   * For macOS and Linux operative systems, this is the program called  "Terminal."

   * For Windows, you have a two main options that should already be installed (I suggest Powershell)

     * Powershell

     * Command Prompt (or cmd.exe)

2. Type `python -V` and press enter.

   * if you got one of these errors, you do not have Python installed:

     * `-bash: python: command not found` 

     *  `'python' is not recognized as an internal or external command` 

     * `python : The term 'python' is not recognized as the name of a cmdlet, function, script file, or operable program.`

     * if you got `Python 2.7.x` you have Python 2 installed

     * if you got `Python 3.x.x` , you have Python 3 installed

       * Make sure you have `Python 3.4.x` or later.
       * Your Python 3 command is `python3`

3. If you have Python 2, try typing `python3 -V` and press enter.

   * if you got one of these same errors you need to install Python 3:

     * -bash: python: command not found` 

     *  `'python' is not recognized as an internal or external command` 

     * `python : The term 'python' is not recognized as the name of a cmdlet, function, script file, or operable program.`

   * if you got `Python 3.x.x` , you have Python 3 installed

     * Make sure you have `Python 3.4.x` or later.
     * Your Python 3 command is `python3`


#### Examples


![Example of checking for Python with Windows Powershell](img/install7.png)

This Windows machine does not have Python or pip


![Example of checking for Python with Windows Powershell](img/install2.png)

This Windows machine does not have Python 3


![Example of checking for Python with Windows Command Prompt](img/install3.png)

This Windows machine has Python 3 using the `python` command


![Example of checking for Python on Mac Terminal](img/install1.png)

This macOS machine has Python 2, but *not* Python 3, so you need to install it



### Windows Machines

1. Visit the Python download page at https://www.python.org/downloads/

2. Download the latest version of the Python installer for Windows

![Screenshot of downloading the Python installer for Windows](img/install4.png)

3. When using the the installer, **make sure the "Add Python 3.7 to PATH" option is checked**

![Screenshot the Python installer where the option to add Python to the path is selected.](img/install8.png)

4. Close all Powershell and Command Prompt windows and reopen one

5. Check for Python with `python -V`

![Screenshot of Python successfully installed on Windows](img/install9.png)

Success!

6. If you installed Python, but were still unable to use in in Powershell or the Command Prompt, you need to add it to your path. You can try the instructions below, or I can help you on the workshop day.

	* Follow the "Setting up Python" instructions here: https://practicaltechnologyforarchives.org/issue7_wiedeman/

	* The Path you need to add is likely to be either:

		* C:\Users\\[USERNAME]\AppData\Local\Programs\Python\Python37-32

		* C:\Python37-32

### macOS Machines

#### Option 1: Using the Terminal

1. Install Xcode if you don't already have it

   a. Check for Xcode by opening the terminal and typing `xcode-select -p` and hit enter

   b. If you get `/Library/Developer/CommandLineTools` you have Xcode and can skip the next steps

   c. Run `xcode-select --install`  to install Xcode. Select the **install** button and agree to install developer tools

   d. Repeat steps a & b

2. Install HomeBrew if you don't already have it

   a. Check for brew with `brew doctor`

   b. If you get `Your system is ready to brew.` you have HomeBrew and can skip the next steps

   c. Run `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"` (You'll probably need to enter your user password.)

   d.  Repeat steps a & b 

3. Install Python 3

   * Run `brew install python3`
   
   * Check your Python version with `python3 -V` 

#### Option 2: Using the Installer

1. Visit the Python download page at https://www.python.org/downloads/

2. Download the latest version of the Python installer for macOS

![Screenshot of downloading the Python installer for macOS](img/install11.png)

3. Follow the instructions for a basic install

4. Check your Python version in Terminal with `python3 -V` 

![Screenshot of Python successfully installed on macOS](img/install12.png)

### Linux Machines

1. Use `sudo apt-get install python3` or `sudo yum install python3` depending on your distro

2. Check your Python version with `python3 -V` 

### Check Your Python 3 Command

* Your Python 3 command will wither by `python3` or `python`
	* If you had an existing version of Python 2 installed, your command will likely be `python3`, otherwise it will be likely just to be `python`

--> If `python -V` returns "Python 3.x.x," then your Python 3 command is `python`

--> If `python3 -V` returns "Python 3.x.x," then your Python 3 command is  `python3`



## 2. Installing ArchivesSnake

* We will use ArchivesSnake to write scripts for ArchivesSpace
* To install ArchivesSnake, run the command that has your correct Python 3 command:
  * `python -m pip install archivessnake`
  * `python3 -m pip install archivessnake`

![Screenshot of ArchivesSnake successfully installed on Windows](img/install10.png)

ArchivesSnake successfully installed on Windows


![Screenshot of ArchivesSnake successfully installed on macOS](img/install13.png)

ArchivesSnake successfully installed on macOS



## 3. Installing a Text Editor

* You should install a text editor if you don't already have one with line numbers and syntax highlighting
* You *can* use Notead or Text Edit, but I would recommend installing something else that will make the code easier to read
* There are many good text editors, including:
	* [Notepad++](https://notepad-plus-plus.org/) (Windows only)
	* [Atom](https://atom.io/)
	* [Sublime Text](https://www.sublimetext.com/)
	* [Visual Studio Code](https://code.visualstudio.com/)



