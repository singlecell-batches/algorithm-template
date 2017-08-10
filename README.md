Reproducible Science
====================

A boilerplate for reproducible and transparent science with close resemblances to the philosophy of [Cookiecutter Data Science](https://github.com/drivendata/cookiecutter-data-science): *A logical, reasonably standardized, but flexible algorithm structure for doing and sharing data science work.*

Requirements
------------
Install `cookiecutter` command line: `pip install cookiecutter`


### Advanced installation
If you want to use environments in `conda`, do:


```
conda create -n cookiecutter -c conda-forge python cookiecutter 
```


Which will produce the output:

```
Fetching package metadata ...............
Solving package specifications: .

Package plan for installation in environment /Users/olgabot/anaconda3/envs/cookiecutter:

The following NEW packages will be INSTALLED:

    arrow:           0.10.0-py36_0 conda-forge
    binaryornot:     0.4.3-py36_2  conda-forge
    chardet:         3.0.4-py36_0             
    click:           6.7-py36_0               
    cookiecutter:    1.5.1-py36_0  conda-forge
    future:          0.16.0-py36_1            
    jinja2:          2.9.6-py36_0             
    jinja2-time:     0.2.0-py36_1  conda-forge
    markupsafe:      0.23-py36_2              
    openssl:         1.0.2l-0                 
    pip:             9.0.1-py36_1             
    poyo:            0.4.1-py36_0  conda-forge
    python:          3.6.2-0                  
    python-dateutil: 2.6.1-py36_0             
    readline:        6.2-2                    
    setuptools:      27.2.0-py36_0            
    six:             1.10.0-py36_0            
    sqlite:          3.13.0-0                 
    tk:              8.5.18-0                 
    wheel:           0.29.0-py36_0            
    whichcraft:      0.4.1-py36_0  conda-forge
    xz:              5.2.2-1                  
    zlib:            1.2.8-3                  

chardet-3.0.4- 100% |##########################################################################################| Time: 0:00:00   3.60 MB/s
future-0.16.0- 100% |##########################################################################################| Time: 0:00:00   6.56 MB/s
poyo-0.4.1-py3 100% |##########################################################################################| Time: 0:00:00 203.05 kB/s
whichcraft-0.4 100% |##########################################################################################| Time: 0:00:00   8.13 MB/s
binaryornot-0. 100% |##########################################################################################| Time: 0:00:00  11.32 MB/s
arrow-0.10.0-p 100% |##########################################################################################| Time: 0:00:00 404.87 kB/s
jinja2-time-0. 100% |##########################################################################################| Time: 0:00:00   3.31 MB/s
cookiecutter-1 100% |##########################################################################################| Time: 0:00:00 310.38 kB/s
#
# To activate this environment, use:
# > source activate cookiecutter
#
# To deactivate an active environment, use:
# > source deactivate
#
```

Usage
-----
To start a new science algorithm, first change to your `singlecell-batches`
directory, which should be in `~/code`:

```
cd ~/code/singlecell-batches
```

From here, run the `cookiecutter` command using this template:

```
$ cookiecutter https://github.com/singlecell-batches/cookiecutter-reproducible-science
```

This proceeds to ask you some questions, for which you type in the answers and
press ENTER to get the next one. The text in brackets indicates the default
values, and the text after the colon indicates my answers, which are not default.

```
full_name [Brian Singlecell]: Olga Botvinnik
email [brian.singlecell@gmail.com]: olga.botvinnik@czbiohub.org
github_username [b-singlecell]: olgabot
algorithm_name [Name of your batch effect correction algorithm]: I got 99 batches
algorithm_slug [i-got-99-batches]: 
algorithm_short_description [A short description of your algorithm]: Finds up to 99 batches in your single-cell RNA-seq data
release_date [2017-08-09]: 
version [0.1.0]: 
```

```
```


If you've run this before, you may get the following question, which it is
totally okay to say "yes" to:

```
You've cloned /Users/olgabot/.cookiecutters/cookiecutter-reproducible-science before. Is it okay to delete and re-clone it? [yes]: yes
```

Project Structure
-----------------

```
.
├── AUTHORS.md
├── LICENSE
├── README.md
├── bin                <- Your compiled model code can be stored here (not tracked by git)
├── config             <- Configuration files, e.g., for doxygen or for your model if needed
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
├── docs               <- Documentation, e.g., doxygen or scientific papers (not tracked by git)
├── notebooks          <- Ipython or R notebooks
├── reports            <- For a manuscript source, e.g., LaTeX, Markdown, etc., or any algorithm reports
│   └── figures        <- Figures for the manuscript or reports
└── src                <- Source code for this algorithm
    ├── data           <- scripts and programs to process data
    ├── external       <- Any external source code, e.g., pull other git algorithms, or external libraries
    ├── models         <- Source code for your own model
    ├── tools          <- Any helper scripts go here
    └── visualization  <- Scripts for visualisation of your results, e.g., matplotlib, ggplot2 related.
```

Check out my latest research algorithm, which successfully applied the `cookiecutter` philosophy: [SEMIC: an efficient surface energy and mass balance model applied to the Greenland ice sheet](https://gitlab.pik-potsdam.de/krapp/semic-algorithm).

License
-------
This algorithm is licensed under the terms of the [BSD License](/LICENSE)
