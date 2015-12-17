![alt tag](http://i.imgsafe.org/22ed408.jpg)

-----------


SEAR: Search Engine for Antimicrobial Resistance
====

Contents
----
[General updates](https://github.com/wpmr2/sear#general-updates)

[Introduction](https://github.com/wpmr2/sear#introduction)

[Versions](https://github.com/wpmr2/sear#versions)

[References](https://github.com/wpmr2/sear#references)

[Contact](https://github.com/wpmr2/sear#contact)

-----------


General updates
====

    1.12.2015:   A Docker container image has been created and it is the easiest way to run SEAR yourself.

-----------


Introduction
====

The aim of this project is to provide an easy to use tool that can construct full-length, horizontally acquired **Antimicrobial Resistance Genes (ARGs)** from sequencing data.

SEAR has been designed with **environmental metagenomics** / **microbiome** experiments in mind, where the diversity and relative abundance of ARGs would like to be determined both quickly and easily.

SEAR outputs: ARG annotation, relative ARG abundance (%), consensus sequence and search results (from ARDB, RAC, NCBI nr and nt databases).

A paper describing the design and implementation of SEAR has been published in [PLoS ONE](http://doi.org/10.1371/journal.pone.0133492).

-----------


Versions
====

There are several versions of SEAR available:

1.	SEAR App
----

+ The SEAR App is due to be published on the BaseSpace platform (Illumina).

+ This is the recommended version to use as it is actively being developed and has the latest version of the SEAR report output.

+ Visit [BaseSpace](https://basespace.illumina.com/apps/2083081/SEAR-Antibiotic-Resistance?preferredversion) to find out more and try the App!


2.	SEAR.docker_version
----

+ The Docker version of SEAR is the version behind the SEAR App. This version of SEAR runs using a 'Docker container' and will have all the required software and dependencies to run properly. An introduction to using Docker can be found [here](https://training.docker.com/).

+ A user can use the SEAR Docker container on a local machine and run SEAR as they would a command line script. 

+ Alternatively, the SEAR Docker container can be run on a server (as in the App version, which uses Amazon cloud servers).

+ The SEAR Docker container image can be pulled directly from the [Docker Hub](https://hub.docker.com/r/wpmr/sear/):

    `docker pull wpmr/sear`

+ Alternatively, the SEAR Docker container image can be built using the Dockerfile:

    `docker build -t 'docker:sear' .`


3.	SEAR.command_line_version
----

+ The original version of SEAR is still available. This is the command line version which requires the user to set up all the required dependencies. It also requires USEARCH still, unlike the other SEAR versions that now use VSEARCH (an open source alternative to USEARCH).

+ The README.md file in SEAR.command_line_version explains how to set up this version of SEAR.

-----------


References
====

SEAR calls on several pieces of bioinformatic software: 


Number | Reference | Function
------ | --------- | --------
1 | [VSEARCH](https://github.com/torognes/vsearch) | `used to quality check, convert and cluster reads`
2 | [BWA-MEM](http://arxiv.org/abs/1303.3997) | `used to map clustered reads to ARG reference sequences`
3 | [SAMtools](http://www.ncbi.nlm.nih.gov/pubmed/19505943) | `used to create ARG consensus sequences from mapped reads`
4 | [BLAST](http://www.ncbi.nlm.nih.gov/pubmed/2231712) | `used to compare ARG consensus sequences to online databases`
5 | [USEARCH](http://www.drive5.com/usearch/) | `used in place of VSEARCH in older SEAR versions`

SEAR requires a database for the initial clustering of reads. This can be a user supplied database (multifasta file) but a copy of the ARG-ANNOT database is included with SEAR and is used by default:

+ [ARG-ANNOT](http://www.ncbi.nlm.nih.gov/pubmed/24145532)

-----------


Contact
====

Please visit the [SEAR Forum](https://groups.google.com/forum/#!forum/sear) to post a question, report a bug or start a discussion.

Alternatively, please send an email to Will Rowe at: [wpmr2@cam.ac.uk](mailto:wpmr2@cam.ac.uk?subject=SEAR).
