# Tips for Data Analyst Report

This repository contains a collection of tips and best practices for creating effective data analyst reports. Whether you are a beginner or an experienced analyst, these tips will help you communicate your findings clearly and effectively.

## 1. Installation by create a python virtual environment
To sepup a python virtual environment for working with data analyst reports, follow these steps:

```bash
# create a new virtual environment
python -m venv .venv
# Activate the virtual environment in windows using gitbash
source .venv/Scripts/activate
```

# create a requirments.txt file and add libraries inside it

# Install required packages
pip install -r requirments.txt
or you can install the packages individually using pip:

```bash
pip install pandas numpy matplotlib seaborn plotly
pip install ipykernel openpyxl
```

## 2. Create a Jupyter Notebook

```bash
# Create a ipynb file
mkdir scripts
cd scripts
touch 01_data_analysis.ipynb
```
# If the commands above not work, your Git Bash "forgot" where its tools are. You can temporarily reset the path in your current terminal session by running:

```bash
export PATH=/usr/bin:/bin:$PATH

After running that, try your original commands again:

mkdir scripts
cd scripts
touch 01_data_analysis.ipynb
```
## 2.1. Use of github copilot for data analytics reports

Here is the prompt no. 1:

> 1. `I have df in this notebook, which has tips data
Act as a data analyst, and write a code using python libraries pandas, numpy, seaborn, matplotlib, and plotly, to do the basic analytics tasks such as:

1. data composition report
2. data distribution report
3. data comparison report
4. data relationship report

if you need to do the statistics please install stats models and scipy libraries using code cells in jupyter notebook.

if you want to create a plot and whenever you do that, please interpret the results as i would like to submit that in a report form.

Lets see whats you have got, i am ready to looking forward to your code without bugs and best possible plots.`

