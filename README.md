# FasParser
#### A package for manipulating sequence data ####

A computer software package called FasParser has been developed for manipulating sequence data. It can be used on personal computers to perform a series of analyses, including counting and viewing differences between two sequences at both DNA and codon levels, identify overlapping regions between two alignments, sort sequences according to their IDs or lengths, concatenate multiple loci sequences for a particular set of samples, translate DNA to protein, construct alignments with multiple different formats, and also some extraction and filtration analyses on a particular FASTA file. Majority of these functions can be run in a batch mode that is much useful for analyzing large data sets. We hope our package will be helpful for a broad audience, particularly those without programming experience in sequence analyses. 

![image](https://github.com/Sun-Yanbo/FasParser/blob/master/Homepage.jpg)

**Sun Yan-Bo** (*sunyanbo@mail.kiz.ac.cn*)

**Kunming Institute of Zoology, Chinese Academy of Sciences**

**DNA-RNA GIF was from https://dribbble.com/shots/1220924-DNA-RNA-GIF

----------

### [System requirement and installation]: ###

- The ‘**FasParser**’ has been developed into a standalone Windows System Application (compiled and tested on Windows 7/10). It could be run on most Windows systems with no dependence of other programs.

- Download the setup program (i.e. ‘**FasParserX.X_setup.exe**’) from https://github.com/Sun-Yanbo/FasParser to your disk, and then double click it to install the whole package. It is normally well using the default installation parameters (clicking the Next button).

### [User guide]: ###

#### 1. Sequence comparison and mutation identification (`Cmp-2Seq`): ####

- The program “**Cmp-2Seq**” in the FasParser package was designed to count and view differences between two DNA sequences at both DNA and codon levels. Under the codon level, the program can also estimate the total number of synonymous (S) and non-synonymous (N) sites for the first sequence and then calculate the number of synonymous and non-synonymous substitutions between the two sequences. 

- Users just need to put two sequences into the two above textboxes and click the Run button. The program could then provide a view the differences between the two sequences in colors and also the summary of identified mutations or substitutions in below region.


#### 2. Alignment comparison and overlapped columns identification (`Cmp-2Align`):  ####

- This program “**Cmp-2Align**” was designed to compare different alignments of ++a same gene++ that might be generated by different aligners. This function needs users to input two alignments through the above scan buttons and click the Run to view their overlaps. The SaveAlign button could save the overlapped regions into an alignment file (in FASTA format).


#### 3. Sequence Sorting (`Sort-ID`):  ####

- This program will allow users to **sort** their FASTA files according to either the IDs, sequence lengths, or a provided list of IDs. Please note that the ID is recognized from the first continuous string of the raw ID. For example, the raw ID in a FASTA file is: 
<br>'Uma\_R000001.2 locus=scaffold79:384179:406202:-'. 
<br>You can use the ID '**Uma\_R000001.2**' to search its sequence, sometime the the ID 'Uma\_R000001' is also ok if there is only targeted ID. If the provided IDs cannot be recognized, there will be no sequence reported.

- With the provided ID list, you can also **rename** the sequence IDs. To achieve that, the ID list should have two columns, the first column refers to the raw ID, and the second column refers to the new ID, as below:

		Uma_R000001.2    R000001.2
		Uma_R000003.2
		Uma_R000002.2    R000002
		...

- In addition, this section also provides a **classification** function, which means that you can use one or more keywords to extract sequences from a raw FASTA file and save them into separate FASTA files. The keywords can be the genus name, species name, or any words that are present in the raw IDs.


#### 4. Sequence concatenation (`MergeFas`): ####

- This program is used to **concatenate** sequences of the same IDs from multiple FASTA files. This program can be run in a batch mode, for which user should define a folder which contains all the FASTA files to merge. **We recommend user to construct alignment before merging, and all files should have a same ID list.**

- There is also a manual mode to **merge two FASTA files**. If the first file has been defined, all the second files (you can change the second file if the previous one has been merged) would be merged recursively to the first file until you click the Save button.


#### 5. Translation from DNA to protein (`Translation`): ####

- This program is used to translate the DNA sequences to protein sequences. There are also two modes available. If users have **lots of FASTA files**, you can use the batch mode to conduct such analyses, during which, you should define a folder which contains the FASTA files to translate. In the manual mode, you can input a **single DNA sequence or a FASTA file**, the program can automate recognize them.


#### 6. Alignment construction and format conversion (`Align-Format`):

- This program is designed to construct the alignment for multiple FASTA files and convert the alignment format to others. There are 3 populat aligners available for use: **Muscle**, **Mafft** and **Prank**. For format conversion, there are 4 different formats available: **FASTA**, **PHYLIP**, **PAML**, and **NEXUS**. Only a batch mode is available. So, you should define a folder name which contains all the aligned FASTA files to perform this analysis.


#### 7. Extraction and filtration (`Fas-Filter`): ####

- This program is designed to perform some extraction and filtration analyses within a particular FASTA file. With this program, you can **extract or remove a set of sequences from the raw FASTA file** based on query IDs and/or the positions per codon, and can also filter the raw FASTA file according to the sequence length.

- In this program, we also provide a function to **cut the raw alignment by removing the columns with many gaps** (‘-’). This function can also fill up the missing data (with ‘N’) at the beginning and end of an alignment, which is useful for some phylogenetic analyses. 

- In addition, this section could also provide a **statistic summary of a raw alignment**, such as showing if there are one or more bad sequences (short) in an alignment and the length of gap-free blocks.

#### 8. Open Reading Frame identification (`getORF`): ####

- This program is designed to identify the ORF for cDNA sequence(s). The cDNA sequences can be organized as **a FASTA file** or **a single sequence**. There are three choice to obtain the ORFs: a) is to get the longest one if there are present more than one potential ORF in the input cDNA sequence; b) is to get all the potential ORF sequences; and c) to get the most similar ORF to one/more protein sequences.

- For identifying ORFs for a FASTA file, if all the sequences in the file encode homologous proteins, only **a single reference protein sequence** (paste into the below textbox) can be used to get the homologous ORFs for all the sequences. 

- If the sequences in FASTA file encode different proteins, like all the cDNA sequences of human genome, the reference protein sequences should be also save into **a FASTA file** and then taken as another input for this program. Moreover, an **ID map file** should be also provided to tell the program which protein sequences is used as reference seq for which cDNA. For example: 

		XM_014583262	XP_014438748
		XM_006166216	XP_006166278
		XM_006141264	XP_006141326
		...	...

	Please note that the 1st and 2nd columns must be IDs for cDNA and protein, respectively.


----------

### [Citation]: ###

**Sun Yan-Bo** FasParser: a package for manipulating sequence data. ***Zoological Research*** 38(2): 110-112, 2017

----------

### [Update history]: ###

[Version 1.2.1] 2017-05-23
1. add auto-update function
2. speed-up the filter functions

[Version 1.2.0] 2017-05-17
1. add Align&Compare function in 'Cmp-2Seq': can handle 2 unaligned sequences;
2. fix bugs in dn/ds estimate when seq length not multiples of 3;
3. fix bugs in format convertion when folder name has space(s);
4. fix some UI errors;
5. improve sort function with seq Length (descending or ascending);
6. improve the display of some results

[Version 1.1.0] 2017-03-28

1. add the getORF function into this package;
1. orf can be get according to ref pep seq(s);
1. optimize some subfunctions;
1. fix some GUI errors;
1. improve the GAP-cut function in `Fas-Filter`;

[Version 1.0.2] 2017-03-22

1. improve the sort function with user provided ID list;
1. improve the extraction function for large FASTA file;
1. add Clear buttons for convenient operation;
1. optimize codes (flexibility and simplicity);
1. fix some bugs
1. add version check function;
1. improve align function for folder with space(s)

[Version 1.0.1] 2017-03-11

1. add classification function in the "Sort-ID" section;
1. add ID-rename function in "Sort-ID" section;
1. improve the alignment cut function in "Fas-Filter" section ;
1. improve the alignment filtration based on seq length;
1. fix bugs
    
[Version 1.0.0] 2017-02-28
