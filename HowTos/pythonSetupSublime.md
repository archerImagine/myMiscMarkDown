# Python Setup for Sublime Text #

As we have already discussed [Complete guide to setup Sublime Text 2 as a best MarkDown Editor.](http://archerimagine.wordpress.com/2014/05/29/complete-guide-to-setup-sublime-text-2-as-a-best-markdown-editor/). In this post I will try to provide you with guidelines to setup Sublime Text 2 for Python Development.

As already mentioned in [Wikipedia](http://en.wikipedia.org/wiki/Python_%28programming_language%29), and I am quoting from there. 

> **Python** is a widely used general-purpose, high-level programming language.Its design philosophy emphasizes code readability, and its syntax allows programmers to express concepts in fewer lines of code than would be possible in languages such as C.The language provides constructs intended to enable clear programs on both a small and large scale.

I stared learning Python because of one of the MIT OCW course which I am trying to complete. Here are some of the links if you want to start learning Python or programming in general.

* [Introduction to Computer Science and Programming | MIT OCW](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-00sc-introduction-to-computer-science-and-programming-spring-2011/)
* [MIT 6.00SC Introduction to Computer Science and Programming | YouTube Link](https://www.youtube.com/course?list=ECB2BE3D6CA77BB8F7)
* [My blog page for MIT OCW Notes](http://archerimagine.wordpress.com/mit-ocw-computer-science/)

All the package information listed below are in the assumption that you have gone through my previous blog post mentioned [here](http://archerimagine.wordpress.com/2014/05/29/complete-guide-to-setup-sublime-text-2-as-a-best-markdown-editor/)

## Default Option in Sublime Text 2 ##
Since Sublime Text itself is written in Python, it is a great editor for any any language, but it takes Python Completely to a different level altogether. There are other alternative for Python development, but if you use Sublime Text you can't just ignore it.

The Default feature which are available in Sublime Text are as follows.

### Command Console ###
In Sublime Text 2 if you press 
````
ctrl + `
````
, then it open up a console, where you can execute all your Python Commands.

### Build System ###
When you have written a Python Code, and you want to build and execute it, Sublime Text provides a default build system for Python under the menu `Tools > Build System > Python`, but this have a small problem.

If you use input or output code in you Python Script, as shown here.  

````
raw_input('Enter your date of birth:')
````

On building this line it will throw the below error.
````
Enter an integer: Traceback (most recent call last):
  File "E:\project\REPOS\myTutorials\Python\MIT6.00SC\Rec_01\src\cubeRoot.py", line 4, in <module>
    x = int(raw_input('Enter an integer: '))
EOFError: EOF when reading a line
[Finished in 1.8s with exit code 1]
````

This error is because Sublime Text does not support input. This problem can be solved using a Plugin which is discussed later.

Here are few reference on this issue, which might be of interest.  

* [Python: EOFError: EOF when reading a line](http://stackoverflow.com/questions/17758782/python-eoferror-eof-when-reading-a-line)
* [Python input EOFError in Sublime Text 2](http://www.bestpythonide.com/python-input-eoferror-in-sublime-text-2.html)


## Plugin required for Python Execution ##

### [SublimeREPL for SublimeText (2 and 3)](https://github.com/wuub/SublimeREPL) ###

As already told there is problem with taking input in a python program in Sublime Text 2. We can solve this problem by installing **SublimeREPL**.

As mentioned in [WikiPedia](http://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop), and I am Quoting here.  

> A read-eval-print loop (REPL), also known as an interactive toplevel or language shell, is a simple, interactive computer programming environment that takes single user inputs (i.e. single expressions), evaluates them, and returns the result to the user; a program written in a REPL environment is executed piecewise. The term is most usually used to refer to programming interfaces similar to the classic Lisp interactive environment. Common examples include command line shells and similar environments for programming languages.

So basically [SublimeREPL](https://github.com/wuub/SublimeREPL), provides that REPL. 

You can Install [SublimeREPL](https://github.com/wuub/SublimeREPL) by using [Package Control](https://sublime.wbond.net/) whose instruction are already mentioned in my [blog](http://archerimagine.wordpress.com/2014/05/29/complete-guide-to-setup-sublime-text-2-as-a-best-markdown-editor/)

So once you have installed [SublimeREPL](https://github.com/wuub/SublimeREPL), you can invoke the **REPL** by invoking Command Palette with `ctrl + Shift + p` and type **SublimeREPL:Python**

Now we have the required REPL, won't it be nice if we can execute our Python Script with the help of this REPL.

The instruction to use this REPL is mentioned in the below link.
* [how to run python code on SublimeREPL](http://stackoverflow.com/a/23722631)

In short these are the steps to follow:- 

* Create a new Build System file, `Tools > Build System > New Build System...`
* The above step will open a file, just copy paste this code

````
{
    "target": "run_existing_window_command", 
    "id": "repl_python_run",
    "file": "config/Python/Main.sublime-menu"
}
````
* Once the above step is done, save the file by the name `SublimeREPL-python.sublime-build`
* After this you can open any Python Script, and select `Tools > Build System > SublimeREPL-python`, and the press `Ctrl + B` which will run the file in the REPL environment.

There is a issue though, once the each time you press `Ctrl + B` to run any Python File, a new REPL tab opens and the it become inactive. The solution to this problem is not known to me.

### [Python Auto-Complete ](https://sublime.wbond.net/packages/Python%20Auto-Complete) ###

One of the best feature of any IDE or Text Editor is AutoComplete Feature. Now we have a Lot of Auto Complete Plugins in Sublime Text. 

The one that blew my mind was [Python Auto-Complete ](https://sublime.wbond.net/packages/Python%20Auto-Complete), the other competitors are .

* [SublimeCodeIntel](https://github.com/SublimeCodeIntel/SublimeCodeIntel)
* [SublimeJEDI](https://github.com/srusskih/SublimeJEDI)

Kindly chose the Auto Complete package based on you preference, since I am Staring out in the Python World, for me [Python Auto-Complete ](https://sublime.wbond.net/packages/Python%20Auto-Complete) was enough because it gives auto completion of inbuilt function and library. 


### [Pylinter](https://github.com/biermeester/Pylinter) ###

**Pylinter** is a linter for python, which can be used with sublime text 2. Now before directly installing **Pylinter** through Package Control, You have to follow these steps irrespective of the OS on which you are running.

#### Prerequisite ####

1. For Mac OS X:-

There is a issue in Mac OS X if **PIP** is not installed so you have to install **PIP** before PyLint.

To Install **PIP** just execute this commands.

````
sudo easy_install pip
````

As mentioned in the **Pylinter** github page, it requires [PyLint](http://www.pylint.org/#install) to installed.

You can visit this page for seeing the instruction to install PyLint on different OS.

* [Install PyLint](http://www.pylint.org/#install)

** For Mac OS X**

The is a correction in installing **PyLint** in the command as mentioned in the install link above, you have to give this command.

````
sudo pip install pylint
````


## References ##
* [Sublime Text 2 tips for Python and web developers](http://opensourcehacker.com/2012/05/11/sublime-text-2-tips-for-python-and-web-developers/)
* [Setting up Sublime Text for Python development ](http://dbader.org/blog/setting-up-sublime-text-for-python-development)
* [Complete guide to setup Sublime Text 2 as a best MarkDown Editor ](http://archerimagine.wordpress.com/2014/05/29/complete-guide-to-setup-sublime-text-2-as-a-best-markdown-editor/)
* [Installing pip on Mac OS X](http://stackoverflow.com/questions/17271319/installing-pip-on-mac-os-x)
* [PyLint - Install ](http://www.pylint.org/#install)
* [PyLinter](https://github.com/biermeester/Pylinter)



