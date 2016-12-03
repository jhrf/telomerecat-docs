Using Telomerecat
=================

Telomerecat estimates telomere length from whole genome sequencing files (WGS). The first step is to scan the input BAM file for any reads that looks even remotely like a telomere. It collects all of these reads and deposits them in a TELBAM. TELBAMs can take around an hour and a half to generate from a BAM file of around 150GB. However, once a TELBAM has been generated, it can be used to quickly generate telomere length estimates. Using these small TELBAMs means you don't need to store a full BAM file to conduct reproducible results. TELBAMS are generated with the command `bam2telbam`.

Once we have generated a TELBAM we can use it to generate a length estimation. This can be done using the `telbam2length`. It usually takes around 2 minutes to generate a length estimate from a TELBAM.

To streamline this process users may wish to conduct both steps using the `bam2length` command. This will take a BAM file as input and output a length estimate .csv file. This command will automatically output TELBAMs for each of the inserted BAM files.


bam2length
++++++++++

The most straightforard way of generating a telomere length estimate from a BAM file is by using the `bam2length` command. This command takes a BAM file and generates a length estimate in a .csv file.

Invoke the `bam2length` command by inputing the following command into your terminal:

.. code-block:: shell
  
    telomerecat bam2length -v2 /path/to/example.bam

The option `-v2` instructs `telomerecat` to print some output to the console. You should substitute a real path name in the place of :code:`path/to/example.bam`.

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

The telbam2length command is used to generate a TL estimate from a TELBAM. 

.. code-block:: shell
  
    telomerecat bam2telbam -v2 /path/to/example.bam

csv2length
++++++++++

`Coming soon`
