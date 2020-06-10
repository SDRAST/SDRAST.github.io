Git
===

Linus Torvalds brilliantly re-invented version control in the form of
`Git <https://en.wikipedia.org/wiki/Git>`_. This is described well in a `Linux
Journal article <https://www.linuxjournal.com/content/git-revision-control-perfected>`_
by Henry Van Styn, and is summarized here.

At the core of the system is a *blob* which has the raw contents of a file.
The name of the file is the hash value obtained from an algorithm known as
`SHA-1 <https://en.wikipedia.org/wiki/SHA-1>`_.  This is a 40-bit hexadecimal
number and is unique.  It is effectively impossible that any two files anywhere
have the same hash value, *unless they are identical*.

A Git *tree* is a file that has a directory listing using these hash values.  
A tree may contain blobs and other trees.  The tree itself is referred to
(named with) its SHA-1 value. The tree does not *contain* the files, it only
refers to them.

A Git repository is a hidden directory called ``.git`` at the top level of
your project's directory.  If you share that project with someone, say by
recursively copying your directory, that person now has a copy of your 
repository. One way of copying the project is with the ``git clone`` command.
The argument for this command is the URL of the remote repository.  The
clone command also creates a reference to the URL called ``origin``.

This is what makes Git brilliant.  Say you have a directory and have a Git tree
that refers to it, and then you make changes in one file.  The changed file
becomes a new blob in your repository. Then you create another Git tree for the 
same but changed directory. The new tree have a different hash value name from 
the previous version of the directory. In your repository you now have one new
blob and one new tree (which is a small file). 

Creating the new file and new tree is done with the command `git commit`.
Git also creates a pointer from the new tree to its parent, which says in effect
"I came from that tree".  The commit action is recorded as the first seven or 
eight digits of the new tree's SHA-1 value.  If for some reason you want to go
back to an earlier version of your project, you get that by using the earlier
commit name.

After you have committed your changes, you can put the changes in the remote 
repository with the command ``git push origin``. If the remote repository
called ``origin`` has changed in the mean time, then this will give an error.
You can get those changes with the command ``git pull origin``.  If Git
cannot seemlessly merge in the changes, they will be flagged for you to resolve.
After you've done that you can ``push``.

Another feature of Git is branching. That is making a copy of the
repository for you to work on without disturbing ``origin``. The `article 
mentioned above 
<https://www.linuxjournal.com/content/git-revision-control-perfected>`_ describes
how to do this, and how to merge your changes back into the original branch.

There are more things to know, like the ``git status`` to see
the current state of your project which will tell you what needs to be done next
and ``git add`` command to tell Git to
include new files into your current project tree.  If all this seems a bit much
then sleep on it and read this again tomorrow.  It's really quite simple.

Tom Kuiper, 2020 Jun 9.
