**README for Calculating Distance Between Alpha Carbons in a PDB File**
---------------------------------------------------------------
Python tool that calculates the distance between two alpha carbons from a PDB file. A tool that accomplishes this task in the language R can be found [here] (https://github.com/calvinrhodes/mbb752_4.1_R). This tool is part of a set of bioinformatic and biological structure tools created for CBB752 at Yale University in the Spring 2016. The website containing the set of tools can be found [here] (http://cbb752spring2016.github.io).

## General
The tool is named distcalc.py. It takes 3 required inputs (inputfile, index1, and index2) and has two optional (outopts, and outputfile) The indices (index1 and index2) correspond to the alpha cabons of the ith and jth residues. The input (inputfile) is the name of a corresponding pdb file from which to calculate the distance. The distance is given in Angstroms. < outopts > allows the user to produce the distance in python to assign to a variable or print out to a text file with the option of including the amino acid sequence comma delimitted.
The tool can be called from both a terminal or inside python with the formatting listed below.

## Usage

Usage:      python3 distcalc.py -i < input file > -a < index of residue 1 > -b < index of residue 2 > -f < output format > -o < .txt output filename >

### Examples:
```{r NCBI_python, engine="python", highlight=TRUE}
# Usage from terminal:
	
    python3 distcalc.py -i sample-input.pdb -a 3 -b 20 -f 2 -o testout.txt 
     
    python3 distcalc.py -i sample-input.pdb -a 3 -b 20 -f 1 -o testout.txt
        
    python3 distcalc.py -i sample-input.pdb -a 3 -b 20 -f 1
            
# In line usage in python:
  	
    python3 
       		
	>>>from distcalc import distance
	
  	>>>dist=distance('1a3n.pdb',3,20,0,'')
```
## Input Formats (-flags):

 * input file (-i):	pdb file of a protein
 * index1 (-a):		integer index of amino acid in sequence to calculate the distance of its alpha C to anothers
 * index2 (-b):		integer index of other amino acid in sequence to calculate the distance of its alpha C to that of index1
 * outopts (-f): 	integer (either 0,1,2) to determine output format, defaults to outputting in line
 	* 0 : outputs distance in angstroms to command line
 	* 1 : outputs distance in angstroms to txt output file
 	* 2 : outputs distance in angstroms to txt output file and amino acid sequence of the protein in the pdb file
 * outputfile (-o):	name of txt file for output options 1 and 2, defaults to "output.txt"
