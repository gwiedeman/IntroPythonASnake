# Installing Python on your local machine

Instructions on how to install Python and make sure its in your PATH so you can run scripts.

## Do I already have Python 3?

There are two main versions of Python, Python 2 and Python 3. We will be using Python 3, and there are very view reasons to still use Python2.

If you are using macOS or a Linux distribution, you probably already have a version of Python installed, but it might be Python 3. If you are using Windows, chances are that you don't have Python installed unless you installed it yourself.

1. To check open a command line terminal. 
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
3. If you have Python 2, try typing `python3 -V` and press enter.
   * if you got one of these same errors you need to install Python 3:
     * -bash: python: command not found` 
     *  `'python' is not recognized as an internal or external command` 
     * `python : The term 'python' is not recognized as the name of a cmdlet, function, script file, or operable program.`
   * if you got `Python 3.x.x` , you have Python 3 installed
     * Make sure you have `Python 3.4.x` or later.
4. Check for pip by running `pip -V` and `pip3 -V`
   * Your version of pip should be the same as your Python version, so if you

![Example of checking for Python on Mac Terminal](img/install1.png)

This macOS machine has Python 2, but not Python 3

![Example of checking for Python with Windows Powershell](img/install7.png)

This Windows machine does not have Python or pip

![Example of checking for Python with Windows Powershell](img/install2.png)

This Windows machine does not have Python 3

![Example of checking for Python with Windows Command Prompt](img/install3.png)

This Windows machine has Python 3 using the `python` command

## Installing Python 3

### Windows Machines

1. Visit the Python download page at https://www.python.org/downloads/
2. Download the latest version of the Python installer for Windows
3. ![Screenshot of downloading the Python installer for Windows](img/install4.png)
4. When using the the installer, make sure the "Add Python 3.7 to PATH" option is checked![Screenshot the Python installer where the option to add Python to the path is selected.](img/install8.png)
5. 

### macOS Machines

### Path 1: Using the Terminal

1. Install Xcode if you don't already have it

   a. Check for Xcode by opening the terminal and typing `xcode-select -p` and hit enter

   b. If you get `/Library/Developer/CommandLineTools` you have Xcode and can skip the next steps

   c. Run `xcode-select --install`  to install Xcode and Agree to **install** developer tools

   d. Repeat steps a & b

2. Install HomeBrew if you don't already have it

   a. Check for brew with `brew doctor`

   b. If you get `Your system is ready to brew.` you have HomeBrew and can skip the next steps

   c. Run `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

   d.  Repeat steps a & b 

3. Install Python 3

   * Run `brew install python3`
   * Check your Python and Pip versions with `python3 -V` and `pip3 -v`

### Path 2: Using the Installer

1. Visit the Python download page at https://www.python.org/downloads/



### Linux Machines

1. Use `sudo apt-get install python3` or `sudo yum install python3` depending on your distro

2. Check your Python and Pip versions with `python3 -V` and `pip3 -v`

## Install Packages

