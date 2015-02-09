Preface - Quickstart
====================

For those who don't want to read the docs before jumping in, try the code snippets below to get going with telomerecat as quickly as possible.

First open your terminal and install telomerecat (if this doesn't work you'll need to read the docs!):

.. code-block:: shell

   sudo pip install telomerecat

Then in your terminal create a directory to run your parabam analysis on:

.. code-block:: shell

   cd ~
   mkdir telomerecat-analysis
   cd telomerecat-analysis

Now let's run telomerecat:

.. code-block:: shell
  
  telomerecat full -v2 /path/to/bam_file.bam

A .csv file with an estimate of length will be produced for your specified BAM file. With these default parameters and depending on how powerful your computer is, expect telomerecat to take an hour to process 1 billion reads.

Installing telomerecat
======================

Hey presto!