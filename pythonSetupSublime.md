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


[how to run python code on SublimeREPL](http://stackoverflow.com/questions/19732006/how-to-run-python-code-on-sublimerepl)

[Python Auto Complte](https://sublime.wbond.net/packages/Python%20Auto-Complete) better than [SublimeCodeIntel](https://github.com/SublimeCodeIntel/SublimeCodeIntel) because of inbuilt function expansion.

[Sublime Text 2 tips for Python and web developers](http://opensourcehacker.com/2012/05/11/sublime-text-2-tips-for-python-and-web-developers/)

sublimeJedi