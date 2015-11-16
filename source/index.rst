.. Telomerecat-docs documentation master file, created by

Welcome to Telomerecat
**********************

:Author: Henry Farmery
:Date: |today|
:Version: |version|

`Telomerecat` estimates the average length of telomeres given whole genome sequencing (WGS) files as input. Length estimation takes into account noise genereated by interstital telomeric sequences and the subtelomere to provide a more accurate estimate. Additioanlly, `Telomerecat` accounts for anneuploidy in WGS samples, without the users having to input an estimate of choromsomes. The biology and technical aspects of WGS are considered in an attempt to only measure true telomereic reads. 

`Telomerecat` is designed to run quickly on either your desktop or remote high powered computing facility. The amount of processors is adjustable to the computing resources available to each user.  

Telomerecat is available as a pre-compiled binary for Linux and MacOSX. Effort has been made to increase backwards compatibility by compiling the binary against old versions of glibc (v2.12). 

If the pre-compiled binary does not work for you can install `Telomerecat` as a normal python package using `pip`:

.. code-block:: shell

   pip install Telomerecat

Telomerecat's python dependancies will be installed automatically, however you will need to ensure that your system has an installed fortran compiler so that scipy will install. It is also good practise to install telomerecat inside a virtualenv (this is best practise for all python pacakges!).

Preface - Quickstart
====================

For those who don't want to read all of the docs before jumping in, try the code snippets below to get going with telomerecat as quickly as possible.

First you'll need to ensure that telomerecat is installed (in most cases you'll just need the pre-compiled binary - check out the Installation section). 

Once you're sure telomerecat is installed, open your terminal and create a directory in which to run your telomerecat analysis:

.. code-block:: shell

   cd ~
   mkdir telomerecat-analysis
   cd telomerecat-analysis

Now let's run telomerecat:

.. code-block:: shell
  
  telomerecat bam2length -v2 /path/to/bam_file.bam

A .csv file with an estimate of length will be produced for your specified BAM file. With these default parameters and depending on how powerful your computer is, expect telomerecat to take an hour and a half to process ~2 billion reads.

Contents:

.. toctree::
   :maxdepth: 2

   Introduction
   EstimatingTelomere
   
Useful Document Links
=====================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
