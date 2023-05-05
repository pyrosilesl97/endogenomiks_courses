---
layout: software
title: Software
permalink: /software/
---

If you are not familiar with the command line, we recommend that you install [R](https://www.r-project.org) and [Rstudio](https://posit.co/download/rstudio-desktop/) on your computer. This will allow you to easily visualize the results of the analysis. 



For convenience, all necessary software will be installed using conda. If this is not installed on the system, it must be installed. For this the click on the following link [conda installation](https://docs.conda.io/en/latest/miniconda.html)

After conda is installed, you will run the following commands to install fastQC and multiQC

```
conda install -c bioconda fastqc 
conda install -c bioconda multiqc 
```

Then we need to install frogs, for this, download the following yaml file in your working directory 
[frogs-conda-requirements.yaml](static_files/codes/frogs-conda-requirements.yaml) and then run the following code: 
```
conda env create --name frogs --file frogs-conda-requirements.yaml
conda activate frogs
```

In case you want to use Kraken, you will need to also run

```
conda install -c bioconda kraken2
```

To download the databases we will need to process the data in FROGS, you can create a directory called 16S_db in the current directory and then download the database, to do this you can use the following code 
```
mkdir 16S_db
cd 16S_db
wget http://genoweb.toulouse.inra.fr/frogs_databanks/assignation/SILVA/16S/silva_138.1_16S.tar.gz
tar -xvf silva_138.1_16S.tar.gz
```

To download the databases we will need to process the data in kraken2, you can create a directory called 16S_db_kraken in the current directory and then download the database, to do this you can use the following code 
```
mkdir 16S_db_kraken
cd 16S_db_kraken
wget https://genome-idx.s3.amazonaws.com/kraken/k2_standard_20230314.tar.gz
tar -xvf k2_standard_20230314.tar.gz
```

Note: This will only download the standard database. 