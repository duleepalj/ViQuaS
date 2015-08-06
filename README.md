# ViQuaS
Viral Quasispecies Spectrum Reconstruction Pipeline

## ViQuaS1.3 programs files and folders:

ViQuaS.R

viquas_files/SSAKE.pl

viquas_files/exactfilter.pl

viquas_files/forwardreads.pl

viquas_files/edge.pl

tools

## Systems software requirements:

ubuntu 12.04 LTS or later

## Application software requirements:

R version 2.14.1 or later

Biostrings version 2.22.0 or later

seqinr version 3.0-6 or later

perl 5.14.2

bioperl 1.6.901-2

## Third party application software requirements:

ssake v3.8

This is included in ViQuas1.3.tar.gz package together with the tools directory.

smalt_i686 (http://www.sanger.ac.uk/resources/software/smalt/)

A pre compiled file is included in ViQuas1.3.tar.gz package inside viquas_files.

New compilation may be needed for a new platform.

## Usage:

Extract ViQuaS1.3.tar.gz

Set the extracted directory (ViQuaS1.3) as working directory

In the command line interface enter the following
	
Rscript ViQuaS.R <reference file in FASTA format> <read file in BAM format> <o> <r> <perform richness (1/0)> <diversityRegionLength>

See Manuscript for setting o and r.

diversityRegionLength = length in bp of the region where the mutations occur.

## Output file:

ViQuaS-Spectrum.fa

Each sequence in this multi-FASTA file is a reconstructed strain.

Each sequence id takes the format of <strain id>_<relative frequency>

ViQuaS-Richness.txt

Ns = estimated total number of strains

Np = estimated number of strains with a relative frequency above f_min. f_min is the totally reconstructible minimum relative frequency of the population.

## Sample Data Set:

sample_reads.bam contains a set of sample reads.

reference.fsa is the corresponding reference sequence.

Running without richness estimation

Rscript ViQuaS.R reference.fsa sample_reads.bam

ViQuaS-Spectrum-Expected.fa is the expected quasispecies spectrum output for this sample data set.

Running with richness estimation

Rscript ViQuaS.R reference.fsa sample_reads.bam 3 0.7 1 1000

ViQuaS-Richness-Expected.txt is the expected richness estimate output for this sample data set.

## Contact Info:

Duleepa Jayasundara

Optimisation and Pattern Recognition Research Group

Department of Mechanical Engineering

Melbourne School of Engineering

The University of Melbourne

Parkville

VIC 3010

Australia

e-mail: d.jayasundara@student.unimelb.edu.au

