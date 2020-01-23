
# GitMiller

GitMiller is a tool for running Jupyter Notebooks from a (partial) Github repository.

## Features

* Downloads (partial) Github repo in your temp folder
* Runs designated notebook
* Cleans up the created temp subfolder

## Installation

`$ pip install gitmiller`

After installation you can use the `gitmiller` command line tool to run your github notebooks.

## Usage

GitMiller uses Papermill to run your remote Notebooks. When a cell contains a 'parameters' tag 


Papermill enables you to override parameters: if a cell contains the tag '


## install
```
pip install git+https://github.com/UtrechtUniversity/EEG-decoding-software.git
```
## uninstall
```
pip uninstall papermill_eeg_decoding
```
## example
```
papermill https://github.com/UtrechtUniversity/EEG-decoding-software/blob/master/examples/proba_penna.ipynb ./a.ipynb -p angle 6.28
```

### compiling 
#### https://packaging.python.org/tutorials/packaging-projects/
> python3 setup.py sdist bdist_wheel