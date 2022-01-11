# Wombat

Wombat is a pipeline for the analysis of Illumina paired-end sequencing data and/or whole bacterial genomes. The development of the workflow is mainly intended for the analysis of Campylobacter jejuni genomes, but, Wombat can work with data of any bacteria. Wombat is created for users without knowledge of bioinformatics or programming, so the ease of installation and execution are the fundamentals of its development. Moreover, Wombat offers you the possibility to select the analysis and the tools you are interested in.

![scheme](https://user-images.githubusercontent.com/58036036/121041162-cb121c80-c7b2-11eb-9527-3bc3757e3a7e.png)

## Installation (Linux)

1. Clone this repository
    ```bash
    $ git clone https://github.com/JoseBarbero/Wombat.git
    ```
1. Go to Wombat's folder
    ```bash
    $ cd Wombat
    ```
1. Create the environment with conda
    ```bash
    $ conda config --append channels conda-forge
    $ conda config --append channels bioconda
    $ conda env create -f wombatenv.yml 
    ```
1. *(On Ubuntu systems you may find missing font problems running Mauve. We recommend you to install the required fonts just in case.)
    ```bash
    $ sudo apt-get install ttf-dejavu
    ```

## How to update Wombat (Linux)

1. Make sure you are not in Wombat conda environment
    ```bash
    $ conda deactivate
    ```
1. Save a copy of your configuration files. Updating Wombat will overwrite you configuration files because this files properties may change with newer versions.

1. Run ./updatewombat
    ```bash
    $ ./updatewombat
    ```

IMPORTANT. After installing or updating Wombat, you need to download the AMRFinder database by running in the Wombat environment:
 ```conda activate wombat
 amrfinder -u
 ```

## How to uninstall Wombat (Linux)

1. Make sure you are not in Wombat conda environment
    ```bash
    $ conda deactivate
    ```
1. Every file in Wombat folder will be deleted. Make sure you don't have anything important in this directory.

1. Run ./uninstallwombat
    ```bash
    $ ./uninstallwombat
    ```


## Set input files and configuration

1.  Set input files in Wombat/input_files.csv (tab as separator):

    | Samples        | Forward           | Reverse  | Genus  | Species  |
    | ------------- |:-------------:|:-----:|:-----:|:-----:|
    | [sample_basename]  | /path/to/your/forward/fastq1_file.fastq | /path/to/your/reverse/fastq1_file.fastq | YourStrainGenus | YourStrainSpecies
    | [sample_basename]  | /path/to/your/forward/fastq2_file.fastq | /path/to/your/reverse/fastq2_file.fastq | YourStrainGenus | YourStrainSpecies
    | [sample_basename]  | /path/to/your/forward/fastq3_file.fastq | /path/to/your/reverse/fastq3_file.fastq | YourStrainGenus | YourStrainSpecies

1. Set your own running parameters and tools to run in "workflow_config.py" file.

1. Default settings are configured for Campylobacter jejuni, if you want to use a different organism, change reference files and configuration file.


## Running the workflow

1. Activate the environment
    ```bash
    $ conda activate wombat
    ```
1. Go to Wombat folder
    ```bash
    $ cd your/path/to/Wombat
    ```
1. Run the workflow
    ```bash
    $ ./wombat
    ```
1. \(*) You can deactivate the environment when you are finished
    ```bash
    $ conda deactivate
    ```

## Output
All files generated by Wombat are stored independently in folders for each tool. For the virulence and antimicrobial resistance genes, a presence/abscence matrix is also generated for the rapid and user-friendly visualization.

## Contact:
For questions, bugs and suggestions, please contact to iortega@ubu.es or jabarbero@ubu.es.

