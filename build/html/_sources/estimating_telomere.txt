Using Telomerecat
=================

Telomerecat estimates telomere length from whole genome sequencing files (WGS). The first step is to scan the input BAM file for any reads that looks even remotely like a telomere. It collects all of these reads and deposits them in a TELBAM. TELBAMs can take around an hour and a half to generate from a BAM file of around 150GB. However, once a TELBAM has been generated, it can be used to quickly generate telomere length estimates. Using these small TELBAMs means you don't need to store a full BAM file to conduct reproducible results. TELBAMS are generated with the command `bam2telbam`.

Once we have generated a TELBAM we can use it to generate a length estimation. This can be done using the `telbam2length`. It usually takes around 2 minutes to generate a length estimate from a TELBAM.

To streamline this process users may wish to conduct both steps using the `bam2length` command. This will take a BAM file as input and output a length estimate .csv file. This command will automatically output TELBAMs for each of the inserted BAM files.


bam2length
++++++++++

The most straightforward way of generating a telomere length estimate from a BAM file is by using the `bam2length` command. This command takes a BAM file and generates a length estimate in a .csv file.

Invoke the `bam2length` command by inputing the following command into your terminal:

.. code-block:: shell
  
    telomerecat bam2length /path/to/example.bam

If output to the command line is desired the option `-v` should be used. You should substitute a real path name in the place of :code:`path/to/example.bam`.

A full list of parameters that can be supplied to this command can be found with the following command:

.. code-block:: shell
  
    telomerecat bam2length --help

The bam2length command is actually just a convenient wrapper for the bam2telbam and telbam2length commands. If working with a large batch of data (where large is more than approximately 5 samples) it is best practise to first generate a batch of TELBAMs using the bam2telbam command and then to run the telbam2length command on the entire batch simultaneously. This will make use of information from within the cohort for F2a correction which may help estimation in low coverage samples.

bam2telbam
++++++++++

Most of the computational effort and time expended during a run of telomerecat is spent generating the TELBAM. Telomerecat must iterate over the entire BAM file to identify all telomere reads. Users may wish to split the time intensive TELBAM generation from the relatively short process of length estimation.

To enable this separation, telomerecat allows the user to generate the TELBAM using a separate command.

.. code-block:: shell
  
    telomerecat bam2telbam /path/to/example.bam

This command is straightforward and takes very few parameters. However, the user should provide the desired number of processing cores to telomerecat using the `-p` option. Specifying more processing cores will enable telomerecat to run more quickly.


telbam2length
+++++++++++++

The telbam2length command is used to generate a TL estimate from a TELBAM or multiple TELBAMs. A TELBAM is simply a subset of all the sequencing reads in the BAM which contain the sequence "TTAGGG" or "CCCTAA" at least twice. The pairs of any of the reads matching the above criteria are also included. 

telbam2length is invoked with the following call to the command line:

.. code-block:: shell
  
    telomerecat telbam2length /path/to/example1_telbam.bam ...

The user may pass multiple TELBAMs to a single run of telbam2length. This will enable telomerecat to run an F2a correction that can help to normalise TL estimates for low coverage or low quality samples. The user can specify NOT to run F2a correction with the `-d` option.

csv2length
++++++++++

`Coming soon`
