CSC cloud manuals
=================

This GitHub repository contains documentation about cloud systems maintained by
`CSC - IT Center for Science <https://www.csc.fi>`_. The documentation uses the
`reStructuredText <http://docutils.sourceforge.net/rst.html>`_ markup language
and the `Sphinx documentation tool <http://sphinx-doc.org/>`_. This README file
describes the process of adding new content using these.

What you will need to install to add new content
------------------------------------------------

This software is required:

* python-pip
* Python devel packages
* Git
* Sphinx
* A text editor of your choosing
* sphinx-autobuild

Installing the required software
--------------------------------

It is assumed that you already have Git and a text editor installed or know how
to install them.

First you will need to install some software to install Sphinx: the Python devel
packages and pip, which is the Python package manager. You can also optionally
install Sphinx through your system's package manager.

Installation on RHEL and derivatives::

        sudo yum install python-devel python-pip

Installation on Ubuntu::

        sudo apt-get install python-dev python-pip

Once you have installed pip and the Python devel packages, you can install
Sphinx and sphinx-autobuild using pip::

        pip install -U Sphinx sphinx-autobuild

Adding new content
------------------

The workflow of editing the documentation is as follows:

1. Start a local web server for previewing documentation (``make livehtml``)
2. Edit documentation in reStructuredText markup
3. Save file(s)
4. Preview documentation in a browser (http://localhost:8000)
5. Go back to step two if necessary and repeat
6. Once satisfied with changes, commit changes to Git (``git commit -a``)

Step 1: Starting the local web server
.....................................

To start the local web server, run this in the source directory where the
Makefile is located and leave the server running::

        make livehtml

This is where sphinx-autobuild is useful. It hosts compiled documentation on a
local webserver and will automatically compile the documentation whenever there
are changes made to the markup files. It will also send a notification to the
browser that is used to access its web server whenever there is a change in the
compiled documentation. It is useful to keep the compiled documentation open in
a browser in one window while editing the source markup files in another window.

Step 2: Editing documentation in reStructuredText markup
........................................................

You can get started with reStructuredText by reading the `reStructuredText
Primer <http://sphinx-doc.org/rest.html>`_ on the Sphinx website. The basics are
fairly simple and it should be easy to pick up if you've ever edited a wiki
using a markup language.

One thing to keep in mind when editing the source markup files is to make lines
a maximum of 80 characters wide. This makes the source files easier to manage
and edit. If you are using vim, you can automatically wrap lines at 80 chars
with these commands::

        :set wrap
        :set tw=80

If you want to wrap a paragraph manually, you can do that by typing "gq" in
normal mode.

Step 3: Save file(s)
....................

When you save, this will trigger an automatic build by sphinx-autobuild and you
should be able to see the results in a browser after a few seconds.

Step 4: Preview documentation in a browser
..........................................

Run a browser on the same machine where sphinx-autobuild is running and point it
to http://localhost:8000. You will be able to see what the documentation will
look like when hosted on a web server.

Step 6: Commit changes to Git
.............................

Once you have a good set of changes ready, you can commit them to Git::

        git add --all
        git commit
        *add a good commit message*

Step 7: Start a build
.............................

Visit https://readthedocs.org/projects/csc-cloud-manuals/ and press "build".
