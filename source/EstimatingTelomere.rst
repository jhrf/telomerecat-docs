Estimating telomere length
==========================

Telomerecat estimates telomere length from whole genome sequencing files. To do this it first scans the input BAM file for anything that looks even remotely like a telomere. It collects all of these reads in a TELBAM. TELBAMs can take around an hour and a half to generate from a BAM file of around 150GB. However, once a TELBAM has been generated, it can be used to quickly generate telomere length estimates. Using these small TELBAMs means you don't need to store a full BAM file to conduct reproducible results. TELBAMS are generated with the command `bam2telbam` (see .

Once we have generated a TELBAM we want to generate a length estimation. This can be done using the `telbam2length`. It usually takes around 2 minutes to generate a length estimate from a TELBAM.

To streamline this process users may wish to conduct both steps using the `bam2length` command. This will take a BAM file as input and output a length estimate .csv file. The user may supply the `-k` option in order to output the TELBAM generated as part of the process.


Generating the TELBAM
+++++++++++++++++++++

.. code-block:: shell
  
    mkdir ~/bin/
    mv ~/bin/
  
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

If you have root permissions on the machine that you hope to run telomerecat on the following command will install telomerecat and all dependencies:

.. code-block:: shell
  
  pip install telomerecat

If this doesn't work because of a permissions error you will need to either gain root permission (try adding sudo infront of the above command) or use a virtual environment. Virtual environments are a very common way of installing and running python based software. Full instructions on downloading and setting up a `python virtual environment may be found here`_. 

.. _python virtual environment may be found here: http://docs.python-guide.org/en/latest/dev/virtualenvs/).



