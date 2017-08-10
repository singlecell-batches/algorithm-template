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

If you used this route, you'll need to activate the environment:

```
source activate cookiecutter
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

The directories for each algorithm comparison are

```
.
├── 00_data
├── 01_notebooks
├── 02_scripts
├── 03_workflows
├── 04_figures
├── AUTHORS.md
├── LICENSE
├── README.md
└── environment.yml
```
Here is a graphical overview of how the data flows between the folders.

![Data flow](/data_flow.png)

Below is a more detailed description of each file/folder

- `00_data` - Input and output data for the project. By default, all files and
  folders here will be ignored by Git because they will tend to be big. If you
  **really** want to include something and its less than 100MB, you can use
  `git add -f data/000_notebookname/filename.csv` to add.
- `01_noteboboks` - All exploratory analyses in the form of Jupyter notebooks.
  Should be named in the order that you did them, e.g.

    ```
    000_combine_data.ipynb
    001_histograms_of_counts.ipynb
    002_combat_test_parameters.ipynb
    ```
- `02_scripts` - Once you've figured out what code you want to write for your
  data, you'll probably have a few standalone R/Python files that you'll want
  to run on your own. e.g.
    ```
    run_combat.py
    measure_before_after_distances.py
    ```
- `03_workflows` - As you figure what you want to compare, you'll probably have
  a common set of scripts from `02_scripts` that you want to run. These
  workflows can reference those scripts and produce outputs into `04_figures`

    ```
    combat_workflow.cwl
    ```
- `04_figures` - PNG or PDF images with graphs produced by either
  `01_notebooks`, `02_scripts` or `03_workflows`, named by the thing that
  produced them, e.g.

    ```
    001_histograms_of_counts/counts.pdf
    001_histograms_of_counts/counts_logged.pdf
    combat_workflow/initial_data/counts.pdf
    combat_workflow/corrected_data/counts.pdf
    run_combat/pca_before.pdf
    run_combat/pca_after.pdf
    ```
- `environment.yml` - Initially empty, but eventually should soon contain the
  installation dependencies for your algorithm. Can be created using `conda env
  export > environment.yml`. The idea is that anyone should be able to
  reproduce your analyses, using your exact packages.

License
-------
This algorithm is licensed under the terms of the [BSD License](/LICENSE)
