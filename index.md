---
title: CS61B Tips and Tricks
layout: default
---
# CS61B Tips and Tricks

## 2/8/16: Style Tip: Changing IntelliJ's Color Scheme

As you've been using IntelliJ in class, you may have been wishing that IntelliJ used a color scheme with a black background, like Josh has set up Sublime to use in lecture.  To change IntelliJ to use a dark background, navigate to IntelliJ's preferences window.  For Mac users, this is under the IntelliJ menu at the top (for some users, it may be called "Settings" instead of "Preferences").  In the search bar at the top, type "theme".  You should see an entry pop up that's called "Appearance". Click "Appearance" and then next to "Theme:", change "Default" to "Darcula". You may need to re-start IntelliJ for the changes to take effect.

![IntelliJ Theme Selection](figures/IntelliJ_Theme.jpg)


## 2/1/16: Never Retype: Up Arrow and Ctrl+R

This week we'll learn two tricks to avoid re-typing commands you've already used.  The first is the up arrow.  Typing the up arrow in Bash will always bring up the previous command you entered.  For example, suppose I tried to add a link to our class's skeleton repository, but I accidentally mispelled it:

<pre>
$ git remote add skeleton https://github.com/Berkeley-CS61B/skeeeton-sp16.git
</pre>

When git gives me an error, it's going to be annoying to retype the entire command (with the typo fixed).  Instead, you can just press the up arrow, and then modify the last part of the command to eliminate the typo.

The second, and more powerful trick, is using Control+r.  If you type Control+r (the control key and the "r" key at the same time), Bash will enter reverse search mode.  In this mode, you can start typing any part of a command you've used in the last, and Bash will autocomplete to the most recent command that had the string you typed as a substring.  If you press Control+r again, Bash will keep going backwards in history to the previous matching command.  For example, suppose I type Control+r and then type "pull":

<pre>
(reverse-i-search)`pull': git pull skeleton master
</pre>

Bash autocompletes to the most recent command I typed that included "pull", which in this case was a git command to pull the latest skeleton code.

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

