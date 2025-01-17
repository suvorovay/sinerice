# SINEsuppl
### This page contains supplementary data for the manuscript
## *"Search for SINE repeats in the rice genome using correlation-based positional weight matrices."*
## Yulia M. Suvorova, Anastasia M. Kamionskaya, Eugene V. Korotkov

### Rice genome analysis

All coordinates presented in tsv format (Chromosome, Begin, End, SineFamilyId, Score, Strand)

- RepeatMasker initial dataset (coordinates of 16421 copies) **O_sativa_RM_160.bed.total.gz**
- HDRSM initial dataset  (coordinates of 40415 copies)  **total_sine_sorted.bed.gz**
- RepeatMasker the final set (coordinates of 14712 copies)  **O_sativa_RM_160_overlap20_uniqid_noDUST.bed.gz**
- HDRSM the final set (coordinates of 15423 copies) **total_overlap20_uniqid_noDUST.bed.gz**


### Simulated dataset analysis 
 Datasets include fasta sequences of simulated chromosomes (\*.fa) and coordinates of inserted SINEs in these sequences (\*.tsv) 
 
- **/FullLengthSet/** folder contains fasta sequences  and coordinates of inserted SINEs in tsv format for the FullLength-test
- **/TrunkatedSet/** folder contains fasta sequences  and coordinates of inserted SINEs in tsv format for the Trunkated-test

#### Results obtained on the simulated datasets

- Repeatamsker results obtained on FullLengthSet (**RepeatMasker_FullLengthSet.tsv.gz**) and TrunkatedSet (**HDRSM_TrunkatedSet.tsv.gz**).
- HDRSM results obtained on FullLengthSet (**HDRSM_FullLengthSet.tsv.gz**) and TrunkatedSet (**HDRSM_TrunkatedSet.tsv.gz**). HDRSM sets include results obtained with different *Kd* values (0.0, -0.5, -1.0, -1.5 and -2.0).

### Executable files 

Executable files for the HDRSM method can be found in the *exe_files* folder. 

The folder contains executable files for Windows for the highly divergent repeat search method (HDRSM). 
HDRSM includes the following steps:

1. Paste your SINE consensus sequence in the fasta format into the "seq.fasta" file.
2. Paste your chromosome of interest in the fasta format into "genome_file.fa".
3. Run xi4.exe by clicking on it to create initial PWM. The additional "data.txt" file will be created, please, do not remove it.
4. Run preob_mat.exe to transform PWM.
5. Run scan_cl4.exe to scan the chromosome ("genome_file.fa") with the obtained PWM. It requires some time. 
	The output file "100.rce" contains the result of scanning for each position. 
	The method includes Monte-Carlo simulations and therefore may return slightly different Z-values on different runs. 
6. Run local_max.exe to collect statistically significant (Z > 10) local max values from the output file 
and transform the results into tsv format (the resulting file is "out.tsv").

The remove_redundancy.exe can be used to remove redundancy from a set of tsv data files found using different SINE consensuses (collected into one file). 
For example in our work the file "total_sine_sorted.bed" contains the results of all 39 SINE consensus search using the remove_redundancy.exe
one will get non-redundant file "non-overlapped.tsv". 




<p> With any questions about the data, please contact Yulia Suvorova (<i>suvorovay@gmail.com</i>) </p>

