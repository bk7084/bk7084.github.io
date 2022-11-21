---
layout: default
title: BK7084 - Computational Simulations
---

# Introduction

Welcome to the BK7084-Computational Simulation. This is a tutorial to
help you setup the Python programming environment so that you can jump
right into the practical courses.

# Coding Environment Setup

## Install a Python interpreter

To run a Python program, you need something called an _interpreter_. This is a piece of software that runs each command in your code. Python is pre-installed on macOS and Linux, while Windows users must
manually install it. You can have multiple installations of Python on the same machine, just like you can have different versions of Microsoft Office or Adobe Photoshop. To manage all these installations and make sure we use the right one, we'll use the Python environment manager [Anaconda](https://www.anaconda.com/) to install Python.

### Install mini-anaconda

#### Windows
1. download the latest Miniconda installer for Windows 64-bit from
<https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links>.
2. Double-click the `.exe` file you just downloaded.
3. Follow the instructions on the screen. If you are unsure about
any setting, accept the defaults. You can always change them later. When
the installation is complete, launch the Anaconda Prompt from the
**Start** menu.
4. To test your installation. Run the `conda list` command from
your Anaconda prompt. A list of installed packages appears if it has
been installed correctly.

#### macOS
1. Download the latest version of Miniconda that matches your computer's processor (Intel or Apple M1) from
<https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links>.
2. Double-click the downloaded installer and then follow the
instructions on the screen.
3. Test your installation. Open up _Terminal_ on your Mac (you can search for the app in Spotlight by pressing command + spacebar), type in `conda` and press Enter. You should see instructions for Conda in your terminal window.

#### Linux

  
Enter your terminal, then follow the steps:

1. Download the latest shell script
```shell
wget -c https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
```
2. Run the installation script then follow the instructions on the
screen
``` shell
sh ./Miniconda3-latest-Linux-x86_64.sh
```
3. To test your installation. In your terminal, run the command
`conda list`. A list of installed packages appears if it has been
installed correctly.

### Create a new Python environment

We can manage Python installations by setting up an _environment_. An _environment_ contains the Python interpreter and some other necessary Python packages. Once an environment is _activated_, anytime you run Python, it will be the version that is installed in that environment with the packages that were installed in that environment.

Inside of your Anaconda Prompt (on Windows) or Terminal (macOS, Linux)  run the following command:

``` shell
conda create --name compsim python=3.9
```

This will create a environment named as **`compsim`**. Of course you
can name it whatever you want. Later we will install some packages
inside of this environment. Right after the creation, you can activate
this environment use

``` shell
conda activate compsim
```

To test if everything works well, type in `python` and press enter in the command prompt/terminal. You should be able to see a python interpreter popped up:

```shell
(compsim) ~/00_introduction > python
Python 3.9.15 (main, Nov 1 2022, 14:18:21) [GCC 12.2.0] on linux
Type "help", "copyright", "credits", or "license" for more information.
>>>
```

## Install Visual Studio Code and the Python Extension

### Visual Studio Code

Go to <https://code.visualstudio.com/Download> and download the
corresponding installer for your system.

![image](assets/images/crashcourse/vscode-download.png)

Once the Visual Studio Code editor is installed, install the Python
extension. Open your Visual Studio Code, and search python in
**Extensions** tab.

![image](assets/images/crashcourse/vscode-ext.png)

### Start VS Code in a project folder

Create an empty folder called *hello*, and open the folder from VS Code:
**Menu** \> **File** \> **Open Folder...**

![image](assets/images/crashcourse/vscode-open.png)

From the File Explorer toolbar, select the **New File** button on the
`hello` folder:

![image](assets/images/crashcourse/vscode-new.png)

Name the file **hello.py**, and it automatically opens in the editor:

![image](assets/images/crashcourse/vscode-newfile.png)

Enter the following source code in **hello.py**:

``` python
print("Hello World")
```

Before we run it, we need to select a Python interpreter: within VSCode,
open the **Command Palette** (*Ctrl+Shift+P*), and then type **Python:
Select Interpreter** command to search, then select the command. The
command presents a list of available interpreters that VS Code can find
automatically, you should be able to see **bk7084-env**, the environment
we just created. Click to choose it. If you don’t see the name
**bk7084-env**, close VS Code, open Ananconda-Prompt then run command

``` bash
conda activate compsim
```

and reopen the VS Code, you should now be able to choose the environment
that we created.

![image](assets/images/crashcourse/vscode-env.png)

Now you can run the script by simply click the **Run Python File in
Terminal** play button in the top-right side of the editor.

![image](assets/images/crashcourse/vscode-run.png)

The button opens terminal panel in which your Python interpreter is
automatically activated, then runs `python hello.py`.

![image](assets/images/crashcourse/vscode-tml.png)

As you can see, the **Hello World** is successfully printed on the
screen in terminal.

# Assignments Setup

To get your assignments, click the **Download assignments** button at the top of the page or go to <https://github.com/bk7084/assignments>,
click **Code** then **Download ZIP**.

![image](assets/images/crashcourse/assignments.png)

Extract the zip file to your preferred location. Open the folder
**00\_introduction** in VS Code, then open the file **into.py**. You can
try to run the file by clicking the **Run Python File** on top-right.
Your terminal probably gives the following error:
*ModuleNotFoundError: No module named ’bk7084’*

![image](assets/images/crashcourse/error_msg.png)

So, what exactly is a Python module? Simply put, a module is a python
file that contains definitions of functions, classes, and variables. In
our case, it means that we need to install this module or package named
**bk7084**.

Open Anaconda-Prompt, then activate **compsim** using

``` bash
conda activate compsim
```

type the following command to install the missing **bk7084** module

``` bash
pip install bk7084
```

***pip*** is the standard package manager for Python. It allows you to
install and manage additional packages that are not part of the Python
standard library.

Once the installation is finished, try again to run the **intro.py**,
you should have a window with a brownish triangle drawn above like this:

![image](assets/images/crashcourse/intro-cap.png)

Congratulations\! You now have a Python environment with necessary
packages to run all the exercises. Continue by reading the page on [Week 1]({% link assignments/Assignment_1.md %}) and finish the exercise.
