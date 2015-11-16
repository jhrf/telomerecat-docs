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

Contents:

.. toctree::
   :maxdepth: 2

   Introduction
   
Useful Document Links
=====================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
