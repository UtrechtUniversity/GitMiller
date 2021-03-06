
# GitMiller

This description can be found [on GitHub here](https://github.com/UtrechtUniversity/GitMiller)

GitMiller is a tool for running Jupyter Notebooks from a (partial) Github repository. It downloads the repository in your temp folder, runs a designated notebook within it, and 
removes all downloaded files afterwards.

## Installation

`$ pip install gitmiller`

After installation you can use the `gitmiller` command-line tool to run your github notebooks.

## Usage

The command-line interface takes the following input parameters:

<table>
<tr>
    <th>parameter</th>
    <th>description</th>
</tr>
<tr>
    <td nowrap>-u, --username</td>
    <td>Username to gain access to GitHub repository</td>
</tr>
<tr>
    <td nowrap>-p, --password</td>
    <td>Password Github repository</td>
</tr>
<tr>
    <td nowrap>-t, --token</td>
    <td>Or use a Github token</td>
</tr>
<tr>
    <td nowrap>-r, --repository</td>
    <td>URL of GitHub repository (can be a subfolder)</td>
</tr>
<tr>
    <td nowrap>-n, --notebook</td>
    <td>filename of notebook you wish to execute, this file must exist in the root folder of the (partially) downloaded folder structure.
    </td>
</tr>
<tr>
    <td nowrap>-o, --output</td>
    <td>local path where GitMiller will put the executed version of your notebook</td>
</tr>
<tr>
    <td nowrap>-c, --config</td>
    <td>local path of YAML file in which you can add all mentioned paramaters</td>
</tr>
</table>

GitMiller uses [Papermill](https://github.com/nteract/papermill) to run your remote notebook. Besides executing, Papermill also enables you to parameterize notebooks. If you would like to override certain variables in your notebook, add the variables and values in the config YAML file under the `papermill` key. See example below.

This repository contains a folder `example` in which a notebook `test.ipynb` exists. If you would like to run this notebook with GitMiller, use either:

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



