Understanding Telomerecat Output
================================

Telomerecat outputs length estimates in the form of a .csv file. The name of the .csv file always takes the form :code:`telomerecat_[UNIXTIME].csv`. This section explains the format of this file.

What follows is a series of sections detailing what each of the columns in the output file means. The sections are organised in order of appearence in the header.

A greater understanding of these terms may be gained from reading the following paper ...(paper forthcoming)

F1
++

This is the amount of `F1` reads in the sample. We can think of F1 reads as reads which are completely telomeric. F1 reads originate from the nucleotide after the boundary to the most distal end of the telomere. 

F2
++

The amount of F2 reads in the sample. F2 reads are reads where one end is completely telomeric and the other is not. Additionally, the completely telomeric end is comprised of the pattern CCCTAA. 

F4
++

The amount of F2 reads in the sample. F4 reads are reads where one end is completely telomeric and the other is not. Additionally, the completely telomeric end is comprised of the pattern TTAGGG.

Psi
+++

This is a measure of fidelity from your sample, it is used in the F2a correction method. The greater this value, the more we believe the observed measurement of F2a. A description of how this variable is derived for each sample is given in the paper.

Insert_mean
+++++++++++

The insert size of the sample. This is either estimated from the TELBAM (default) or input by the user.

Insert_sd
+++++++++

The standard deviation of the insert size. As for the mean, this is either estimated from the TELBAM (default) or input by the user.

F2a
+++

F2a reads are the estimated number of reads covering the boundary between telomere and nontelomere. The number is given by F2 - F4. The logic being that any F4 read is known to have come from an interstitial or subtelomere region. Any F4 read will have a companion F2. By subtracting F4 from F2 we find the approximate number of reads without a F4 companion. These are reads over the boundary. A more 

F2a_c
+++++

This is F2a count used in the simulation, it represents the number of F2a reads after undergoing batch correction. If F2a correction is disabled by the user, this number will be the same as F2a.

A full description of the F2a correction formula is given in the paper.

Length
++++++

The telomere length as estimated by telomerecat. Length is output in basepairs
