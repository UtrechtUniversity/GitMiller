
# GitMiller

GitMiller is a tool for running Jupyter Notebooks from a (partial) Github repository. It downloads the repository in your temp folder, runs a designated notebook within it and removes all downloaded files afterwards.

## Installation

`$ pip install gitmiller`

After installation you can use the `gitmiller` command-line tool to run your github notebooks.

## Usage

The command-line interface takes the following input parameters:

| parameter | description |
| --- | --- |
| -u,<br />--username | Username to gain access to GitHub repository |
| -p,<br />--password | Password Github repository |
| -r,<br /> --repository | URL of GitHub repository |
| -n,<br />--notebook | filename of notebook you wish to execute, this file must exist in the root of the (partially) downloaded folder structure.|
| -o,<br />--output | local path where Papermill will put an executed version of your notebook |
| -c,<br />--config | local path of YAML file in which you can add all mentioned paramaters |

GitMiller uses [Papermill](https://github.com/nteract/papermill) to run your remote notebook. Besides executing, Papermill also enables you to parameterize your notebooks. If you would like to override certain variables in your notebook, add the variables and values in the config YAML file

This repo contains a folder `example` in which a notebook `test.ipynb` exists. If you would like to run this notebook with GitMiller, use either:

```
$ gitmiller -u <GITHUB USERNAME> -p <GITHUB PASSWORD>, -r https://github.com/UtrechtUniversity/GitMiller/tree/master/example, -n test.ipynb, -o <LOCAL OUTPUT-PATH>
```
or create the following YAML file:
```
repository: https://github.com/UtrechtUniversity/GitMiller/tree/master/example
username: <GITHUB USERNAME>
password: <GITHUB PASSWORD>
notebook: test.ipynb
output: <LOCAL OUTPUT-PATH>

papermill:
  a: 10
  b: 60
```
and run with:
```
$ gitmiller -c <PATH TO YAML-FILE>
```



