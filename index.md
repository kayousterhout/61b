---
title: CS61B Tips and Tricks
layout: default
---
# CS61B Tips and Tricks

## 1/25/16: Tab Completion

One of the most useful Bash tricks is tab completion.  You'll often find yourself typing a filename in the terminal; for example, to add a file to git.  If you start typing a filename and then press Tab, Bash will automatically complete the filename for you based on what's in the directory.  Suppose I have a bunch of long filenames in my current directory:

<pre>
$ ls
another_filename_that_is_also_long         
another_really_long_filename_that_is_even_longer
really_long_filename
</pre>

If I want to add `really_long_filename` to git, I can start typing the filename:

<pre>
$ git add rea
</pre>

and then press Tab, and bash will fill this in to:

<pre>
$ git add really_long_filename
</pre>

What if I press Tab after entering in an ambiguous prefix? For example, suppose I type

<pre>
$ git add an
</pre>

and then press Tab.  In this case, Bash will fill in as much as it can:

<pre>
$ git add another_
</pre>

but then stops, because it doesn't know which of the files beginning with `another_` I'm trying to type.  If I press Tab a second time, Bash will list the possible files:

<pre>
$ git add another_
another_filename_that_is_also_long
another_really_long_filename_that_is_even_longer
</pre>

Now I can continue typing the filename (e.g., adding an `f` to add `another_filename_that_is_also_long`) and press Tab again.

This trick also works with commands! Suppose you've forgotten what language we're using in this class, so you can't remember how to run your program (is it `java` or `jabba`???).  If you start typing the name of the command and then press Tab, Bash will show you all of the options:

<pre>
$ ja
jadetex         jar             java            javadoc         javah           javaws          jamo-normalize  jarsigner       javac           javafxpackager  javap 
</pre>

This tip was inspired by a page on [How-To Geek](http://www.howtogeek.com/110150/become-a-linux-terminal-power-user-with-these-8-tricks/) that you can check out for more tips!

