Estimating telomere length
==========================

Telomerecat estimates telomere length from whole genome sequencing files. To do this it first scans the input BAM file for anything that looks even remotely like a telomere. It collects all of these reads in a TELBAM. TELBAMs can take around an hour and a half to generate from a BAM file of around 150GB. However, once a TELBAM has been generated, it can be used to quickly generate telomere length estimates. Using these small TELBAMs means you don't need to store a full BAM file to conduct reproducible results. TELBAMS are generated with the command `bam2telbam` (see .

Once we have generated a TELBAM we want to generate a length estimation. This can be done using the `telbam2length`. It usually takes around 2 minutes to generate a length estimate from a TELBAM.

To streamline this process users may wish to conduct both steps using the `bam2length` command. This will take a BAM file as input and output a length estimate .csv file. The user may supply the `-k` option in order to output the TELBAM generated as part of the process.


bam2length
++++++++++

The most straightforard way of generating a telomere length estimate from a BAM file is by using the `bam2length` command. This command takes a BAM file and generates a length estimate in a .csv file.

Invoke the `bam2length` command by inputing the following command into your terminal:

.. code-block:: shell
  
    telomerecat bam2length -v2 /path/to/example.bam

The option `-v2` instructs `telomerecat` to print some output to the console. You should substitute a real path name in the place of :code: `path/to/example.bam`.

Depending on the size of your BAM file, `telomerecat` will produce as estimate of length along with other vital statistics. 

A full list of parameters that can be supplied to this command can be found with the following command:

.. code-block:: shell
  
    telomerecat bam2length --help

bam2telbam2
+++++++++++

Most of the computational and time expended during a run of telomerecat is spent generating the TELBAM. Telomerecat must iterate over the entire BAM file to identify all telomere reads. Users may wish to split the time intensive TELBAM generation from the reletively short process of length estimation.

To enable this seperation, telomerecat allows the user to generate the TELBAM using a seperate command.

.. code-block:: shell
  
    telomerecat bam2telbam -v2 /path/to/example.bam
  

telbam2length
+++++++++++++

`Coming soon`

Understanding Telomerecat Output
================================

Telomerecat outputs length estimates in the form of a .csv file. The name of the .csv file always takes the form :code: `telomerecat_[UNIXTIME].csv`. This section explains the format of this file.

What follows is a series of sections detailing what each of the columns in the output file means. The sections are organised in order of appearence in the header.

A greater understanding of these terms may be gained from reading the following paper ...(paper forthcoming)

F1
++

This is the amount of `F1` reads in the sample. F1 reads orginiationg from the base after the boundary to the most distal end of the telomere. 

F2a
+++

`Coming soon`


