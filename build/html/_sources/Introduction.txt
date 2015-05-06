Preface - Quickstart
====================

For those who don't want to read the docs before jumping in, try the code snippets below to get going with telomerecat as quickly as possible.

First open your terminal and install telomerecat (if this doesn't work you'll need to read the docs!):

.. code-block:: shell

   sudo pip install telomerecat

Then in your terminal create a directory in which to run your telomerecat analysis:

.. code-block:: shell

   cd ~
   mkdir telomerecat-analysis
   cd telomerecat-analysis

Now let's run telomerecat:

.. code-block:: shell
  
  telomerecat bam2length -v2 /path/to/bam_file.bam

A .csv file with an estimate of length will be produced for your specified BAM file. With these default parameters and depending on how powerful your computer is, expect telomerecat to take an hour to process ~2 billion reads.

Installing telomerecat
======================

There are several ways to install telomerecat. Perhaps the easiest is to download the relevant binary and run telomerecat straight away. Other methods, which tie in with conventional ways to install python programs are available.

Install telomerecat as precompiled binary
+++++++++++++++++++++++++++++++++++++++++

The easiest way to use telomerecat is to download one of the precompiled binaries listed here (link to binaries). All you need to do is download the binary for your system and then navigate to the file on your system and use a terminal command to start the program. This will be second nature to those experienced with the command line. If you need a little more help with installation the next few paragraphs can introduce you to some of the basics.

The rest of these instructions are intended to help novices get the binary installed and working on the command line. We will install telomerecat to an easy to access location on the users computer.

To start, follow the link above and download the binary for your system. The telomerecat binary will then download to your computer and will be in a folder with all your other downloads (on MacOSX this folder is "~/Downloads/" [#f1]_). Now open the `Terminal` on your computer. Once Terminal is open type the following: 

.. code-block:: shell
  
    mkdir ~/bin/
    mv ~/bin/
    
This will create a new directory in which to store telomerecat.

Now enter this block of code into your Terminal window [#f2]_:

.. code-block:: shell

    cp ~/Downloads/telomerecat-macosx-XX ./
    mv ./telomerecat-macosx-XX ./telomerecat

This will move telomerecat into the directory we created and will give it a more easily referenced name (we can now refer to it as telomerecat rather than with all the extraneous platform and version details).

Finally, enter this:

.. code-block:: shell

    chmod +x ./telomerecat

This tells your system that it's ok to "exectue" (or, run) the file.

To test that all this has worked simply type the following:

.. code-block:: shell

    ~/bin/telomerecat

If you see the telomerecat welcome message you have succesfully installed telomerecat! If not, make sure you followed the steps correctly. If you can't get this install to work please try some of the options listed in the following sections.

  
.. rubric:: Footnotes

.. [#f1] These instructions assume that the user is using a Mac. The instructions are almost identical aside from the binary will be different and the starting Download location may be different.
.. [#f2] Where it says `telomerecat-macosx-XX` you should use the actual name of the file you downloaded.

Install using pip
+++++++++++++++++

`telomerecat` can be installed on most systems using pip (just like thousands of other python programs).

`pip` is a platform for installing python packages from the Python Package Index. It is widely available and comes as standard with many distribtuions of Mac OSX and Linux. You probably already have this program on your computer. Try typing the following in your console to see if you have `pip` installed:

.. code-block:: shell
  
  pip -V

If pip is installed on your system you should see some text describing the version of pip installed on your system. If your terminal reports that the command is not found you'll have to either install pip (instructions are readily available on the web) or use one of the other installation methods.



