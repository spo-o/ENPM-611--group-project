# ENPM611 Project Application Template

This is the template for the ENPM611 class project. Use this template in conjunction with the provided data to implement an application that analyzes GitHub issues for the [poetry](https://github.com/python-poetry/poetry/issues) Open Source project and generates interesting insights.

This application template implements some of the basic functions:

- `data_loader.py`: Utility to load the issues from the provided data file and returns the issues in a runtime data structure (e.g., objects)
- `model.py`: Implements the data model into which the data file is loaded. The data can then be accessed by accessing the fields of objects.
- `config.py`: Supports configuring the application via the `config.json` file. You can add other configuration paramters to the `config.json` file.
- `run.py`: This is the module that will be invoked to run your application. Based on the `--feature` command line parameter, one of the three analyses you implemented will be run. You need to extend this module to call other analyses.

With the utility functions provided, you should focus on implementing creative analyses that generate intersting and insightful insights.

In addition to the utility functions, an example analysis has also been implemented in `example_analysis.py`. It illustrates how to use the provided utility functions and how to produce output.

## Setup

To get started, your team should create a fork of this repository. Then, every team member should clone your repository to their local computer. 


### Install dependencies

In the root directory of the application, create a virtual environment, activate that environment, and install the dependencies like so:

```
pip install -r requirements.txt
```

### Download and configure the data file

Download the data file (in `json` format) from the project assignment in Canvas and update the `config.json` with the path to the file. Note, you can also specify an environment variable by the same name as the config setting (`ENPM611_PROJECT_DATA_PATH`) to avoid committing your personal path to the repository.


### Run an analysis

With everything set up, you should be able to run the existing example analysis:

```
python run.py --feature 0
```

That will output basic information about the issues to the command line.


## VSCode run configuration

To make the application easier to debug, runtime configurations are provided to run each of the analyses you are implementing. When you click on the run button in the left-hand side toolbar, you can select to run one of the three analyses or run the file you are currently viewing. That makes debugging a little easier. This run configuration is specified in the `.vscode/launch.json` if you want to modify it.

The `.vscode/settings.json` also customizes the VSCode user interface sligthly to make navigation and debugging easier. But that is a matter of preference and can be turned off by removing the appropriate settings.

## Feature 1 - Montly Issue Analyser
The Monthly Issue Analyser is a feature that can be used to analyze the count of issues created each month, this is based on created_date field in poerty_issues.json file. This functionality takes 4 digit year as input and generates the bar graph that depicts the count of issues created for each month in that specified year. If input is blank then it aggregates the data across all years avaialble in poerty_issues.json file and plots the bar graph.

## To run the Monthly Issue Analyser

```
python run.py --feature 1
```
This will ask for 4 digit year input when run in the terminal.


## Feature 2 - Top Labels Analyzer
The Top Labels Analyzer is a feature that can be used to analyze and visualize the usage of labels in  poerty_issues.json file. This functionality allows users to either:
-> Search for a specific label by providing its label as input, or
-> View the top 50 labels used in the issues if no specific label is provided.
The analysis is based on the labels field of the issues in the dataset, and the results are visualized in the form of a bar chart.

## To run the Monthly Issue Analyser

```
python run.py --feature 2
```
This will need a string as a input for searching lables in the dataset.

## Feature 3 - User-Specific Issue Contribution Analyzer

The User-Specific Issue Contribution Analyzer is a feature designed to track and display the contributions of a specific user within the poetry_issues.json file. It provides insights into:

The number of issues created by a specific user.
The creation dates of these issues.
The labels associated with each issue created by the user.
This feature is particularly useful for project managers and team leads who need to assess individual contributions over the course of a project.

## To run the Monthly Issue Analyser

```
python run.py --feature 3
```
This will need a string as a input that is User name.

