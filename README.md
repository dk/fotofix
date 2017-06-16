# FotoFix - simple image viewer

FotoFix is a simple image viewer with simple capabilities to take care of
freshly downloaded photos from your camera - can walk image lists, rotate
images, and remove red eyes (with some luck). It was inspired by IrfanView for
Windows, a great but unfortunately non-portable and closed-source product. My
experience with various image viewers came to a point where I was no longer
satisfied with any, so I wrote yet another one.

Installation
------------

FotoFix requres perl, Prima, and IPA as dependencies. Whereas the first
can be obtained by typing "download perl" in Google, the latter are
available from CPAN.

Usage
=====

Remove red eyes
---------------

To remove red eyes, select a rectangular area by mouse and do
"Edit/Effects/Remove red eyes". This will hopefully eliminate red spots in the
given rectangle. If there are false positives, try to reload the image and
apply the operation to a smaller area. The algorithm for reducing red eye glow
is very simple, so if you have some bad red eyes, not detectable by it, feel
free to hack it.

Show pixel value under cursor
-----------------------------

Press shift and move the mouse around the picture

Magnifying glass
----------------

Press middle button. To change zoom, rotate the mouse wheel. The mouse pointer
gets hidden, but press shift and move the pointer to show it back. If the
middle button is pressed together with Ctrl, then the magnifying glass is
double size.

Execute
-------

When executing a command for each tagged image, the following substitution
rules apply. If $_ is found the command, the command is iterated for each
tagged file and $_ is substituted to the filename. If $* is found, then a
single command is executed, where $* is substitled to a list of all tagged
files. Both $* and $_ cannot be specified simultaneously. If neither is
specified, $* is assumed to be appended to the end of the command.

External commands
-----------------

Specify an external command that will be executed on Alt+num shortcut on the
currently opened file. The syntax allows $_ wildcard globbing to specify
exactly where the file name will appear. Set empty string to delete the command
shortcut.

Rename
------

Apply a substitutive perl regular expression to each file, where each filename
will be stored in $_, and file index in $..

Bugs & features
===============

The viewer is very, very simple. If you find a bug, or miss a feature, you are
very welcome to hack it as you like, and eventually send me a patch.

License
=======

This software is distributed under BSD license

Author
======

Dmitry Karasik, <dmitry@karasik.eu.org>.

