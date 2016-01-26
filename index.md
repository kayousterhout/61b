---
title: CS61B Tips and Tricks
layout: default
---
# CS61B Tips and Tricks

## 1/25/16: Tab Completion

One of the most useful Bash tricks is tab completion.  You'll often find yourself typing a filename in the terminal; for example, to add a file to git.  If you start typing a file name and then press Tab, Bash will automatically complete the filename for you based on what's in the directory.  Suppose I have a bunch of long filenames in my current directory:

```
$ ls
another_filename_that_is_also_long         
another_really_long_filename_that_is_even_longer
really_long_filename
```

If I want to add `really_long_filename` to git, I can start typing the filename:

```
$ git add rea
```

and then press Tab, and bash will fill this in to:
```
$ git add really_long_filename
```

What about if I press Tab after entering in an ambiguous prefix? For example, suppose I type
```
$ git add an
```
and then press Tab.  In this case, Bash will fill in as much as it can:
```
$ git add another_
```
but then stops, because it doesn't know which of the files beginning with `another_` you're trying to type.  If you press Tab a second time, Bash will show you a list of the possible files:
```
$ git add another_
another_filename_that_is_also_long
another_really_long_filename_that_is_even_longer
```
Continue typing the filename and press tab again, and Bash will fill the rest in for you.

This trick also works with commands! Suppose you've forgotten what language we're using in this class, so you can't remember how to run your program (is it `java` or `jabba`???).  If you start typing the name of the command and then press Tab, Bash will show you all of the options:
```
$ ja
jadetex         jar             java            javadoc         javah           javaws          
jamo-normalize  jarsigner       javac           javafxpackager  javap 
```
The traces labeled as TPC-DS ran a modified version of the [TPC-DS benchmark](http://www.tpc.org/tpcds/).

This tip was inspired by a page on [How-To Geek](http://www.howtogeek.com/110150/become-a-linux-terminal-power-user-with-these-8-tricks/) that you can check out for more tips!

