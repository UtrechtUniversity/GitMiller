
# GitMiller

GitMiller is a tool for running Jupyter Notebooks from a (partial) Github repository. It downloads the repository in your temp folder, runs a designated notebook within it and removes all downloaded files afterwards.

## Installation

`$ pip install gitmiller`

After installation you can use the `gitmiller` command-line tool to run your github notebooks.

## Usage

The command-line interface takes the following input parameters:

| parameter | description |
| --- | --- |
| -u, --username | Username to gain access to GitHub repository |
| -p, --password | Password Github repository |
| -r, --repository | URL of GitHub repository |
| -n, --notebook | filename of notebook you wish to execute, this file must exist in the root of the (partially) downloaded folder structure.|
| -o, --output | local path where Papermill will put an executed version of your notebook |
| -c, --config | local path of YAML file in which you can add all mentioned paramaters |

GitMiller uses [Papermill](https://github.com/nteract/papermill) to run your remote notebook. Besides executing, Papermill also enables you to parameterize your notebooks. If you would like to do the latter, you have to add the parameters you wish to override in the config YAML file.

Example