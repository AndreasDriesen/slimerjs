.. index:: Installation


============
Installation
============

Installation of SlimerJs
------------------------

.. index::  ArchLinux

A `package is available for Arch Linux <https://aur.archlinux.org/packages/slimerjs/>`_,
thanks to a contributor. So if you use Arch Linux just type in a terminal:

.. code-block:: bash

    yaourt slimerjs

It will install all needed packages. You can then jump to the
:ref:`Lauching Slimerjs <launch>` section.

With others operating systems, download the latest zip package of SlimerJS
`from the website <http://slimerjs.org>`_ and extract files into a directory
somewhere on your disk. You'll have a ``slimerjs/`` directory with some files and
a script ``slimerjs`` (and ``slimerjs.bat`` for Windows).


Installation of Firefox or Xulrunner
------------------------------------

.. index:: Firefox, XulRunner

SlimerJS runs on any platform on which Firefox (Desktop version) is available.
It needs XulRunner or Firefox. So install them first, for your prefered operating system.

- `Download Firefox <http://getfirefox.com>`_ (version 18 or higher)
- or `Download Xulrunner <http://ftp.mozilla.org/pub/mozilla.org/xulrunner/releases/19.0.2/runtimes/>`_ (version 18 or higher)

Configuring SlimerJs
------------------------

During its launch, SlimerJS tries to discover itself the path of Firefox or
XulRunner. In case it fails, you should create an environment variable
containing the path of the Firefox/XulRunner binary. To create this environment
variable from a command line:

- On linux:
   .. code-block:: bash

      export SLIMERJSLAUNCHER=/usr/bin/firefox
- on Windows
   .. code-block:: text

      SET SLIMERJSLAUNCHER="c:\Program Files\Mozilla Firefox\firefox.exe
- On windows with cygwin
   .. code-block:: bash

      export SLIMERJSLAUNCHER="/cygdrive/c/program files/mozilla firefox/firefox.exe"
- On MacOS
   .. code-block:: bash

      export SLIMERJSLAUNCHER=/Applications/Firefox.app/Contents/MacOS/firefox


You can of course set this variable in your .bashrc, .profile or in the computer
properties on Windows.

.. _launch:

Launching SlimerJS
------------------

From a command line, call the <code>slimerjs</code> executable with the path
of a javascript file.

.. code-block:: bash

    /somewhere/slimerjs-1.2.3/slimerjs myscript.js

On Windows:

.. code-block:: text

    c:\somewhere\slimerjs-1.2.3\slimerjs.bat myscript.js

The js script should contain your instructions to manipulate a web page...

You can indicate several options on the command line. See the "configuration" chapter.

Having a headless SlimerJS
--------------------------

There is a tool called xvfb, available on Linux and MacOS. It allows to launch
any "graphical" programs without the need of an X-Windows environment. Windows of
the application won't be shown and will be drawn only in memory.

Install it from your prefered repository (``sudo apt-get install xvfb`` with debian/ubuntu).

Then launch SlimerJS like this:

.. code-block:: bash

    xvfb-run ./slimerjs myscript.js

You won't see any windows. If you have any problems with xvfb, see its
documentation.
