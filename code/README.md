The attached CSVs contain the predictions given by the different predictors presented in:

[1] A. Begga, Ò. Garibo-i-Orts, S. de María-García, F. Escolano, M.A. Lozano, N. Oliver, and J.A. Conejero. Predicting COVID-19 pandemic waves, including vaccination data with deep learning

Our models have been trained and tested in countries where the number of administered vaccines per day and type were available from January 1st, 2021, to April 30th, 2021. These are the countries considered in this work: Argentina, Austria, Belgium, Bulgaria, Canada, Croatia, Cyprus, Czech Republic, Denmark, Ecuador, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Luxembourg, Netherlands, Norway, Poland, Portugal, Slovak Republic, Slovenia, Spain, Sweden, Switzerland, and the United States.

All CSVs have the same structure (columns):

  - Truth: real number of cases

  - Prediction: predicted number of cases

  - Date

  - Country

  - Month (for plotting purposes)

  - Year (for plotting purposes)

We detail the content of each CSV file:

  - baseline.csv: Predictions by the baseline model from 01-01-201 to 30-04-2021. No waning immunity to COVID-19 from illness is considered.

The following models consider the waning immunity of COVID-19 from illness. They differ on considering (or not)
1 - the vaccination policy as described in the Oxford Covid-19 Government Response Tracker https://www.bsg.ox.ac.uk/research/covid-19-government-response-tracker
2- vaccination data
3- waning immunity from vaccination

Vaccination data can only be implemented through an SVIR model.

These are the models labeled as in Table 1 of our work:

  - woH7_woVacW_SIR: Information of the NPI H7 from the OxGRCT has NOT been included. No other vaccination data has been included.

  - woH7_woVacW_SVIR: Information of the NPI H7 from the OxGRCT has NOT been included. Vaccination data has been included, but the waning immunity of vaccines has NOT been included.

  - woH7_VacW_SVIR: Information of the NPI H7 from the OxGRCT has NOT been included. Vaccination data has been included, and the waning immunity from vaccines has also been considered.

  - H7_woVacW_SIR: Information of the NPI H7 from the OxGRCT has been included. No other vaccination data has been included.

  - H7_woVacW_SVIR: Information of the NPI H7 from the OxGRCT has been included. Vaccination data has been included, but the waning immunity of vaccines has NOT been included.

  - H7_VacW_SVIR: Information of the NPI H7 from the OxGRCT has been included. Vaccination data has been included, and the waning immunity from vaccines has also been considered.

# IA4COVID: Predicting the COVID19 pandemic
curve with vaccination

## Introduction
In this paper, we present a deep learning-based approach to
predict the number of daily COVID-19 cases in over 170 countries in the
world, taking into account the non-pharmaceutical interventions (NPIs)
applied in those countries, including vaccination.
We also describe a novel prescriptor of NPIs to minimize the expected
number of COVID-19 cases while minimizing the social and economic
cost of applying such interventions. We empirically validate the proposed
approach for six months between January and June 2021, once vaccination
is available and applied in most countries. Our model outperforms state-of-
the-art methods and opens the door to accurate, scalable, and data-driven
approaches to modeling the pandemic curve.
Within this repository you will find:
* Sample predictors and prescriptors 
* Sample implementations of the "predict" API and the "prescribe" API, which you will be required to implement 
as part of your submission
* Sample IP (Intervention Plan) data to test your submission

## Pre-requisites
To run the examples, you will need:
* A computer or cloud image running a recent version of OS X or Ubuntu (Using Microsoft Windows™.) 
* Your machine must have sufficient resources in terms of memory, CPU, and disk space to train machine learning models 
and run Python programs.
* An installed version of Python, version ≥ 3.6. To avoid dependency issues, we strongly recommend using a standard Python [virtual environment](https://docs.python.org/3/tutorial/venv.html) with `pip` for package management. The examples in this repo assume you are using such an environment.

Having registered for the contest, you should also have:
* A copy of the Competition Guidelines
* Access to the Support Slack channel
* A pre-initialized sandbox within the XPRIZE system

## Examples
Under the `covid_xprize/examples` directory you will find some examples of predictors and prescriptors that you can 
inspect to learn more about what you need to do:
* `predictors/linear` contains a simple linear model, using the 
[Lasso algorithm](https://en.wikipedia.org/wiki/Lasso_(statistics)).
* `predictors/lstm` contains a more sophisticated [LSTM](https://en.wikipedia.org/wiki/Long_short-term_memory) 
model for making predictions.
* `prescriptors/zero` contains a trivial prescriptor that always prescribes no interventions; 
`prescriptors/random` contains one that prescribes random interventions.
* `prescriptors/neat` contains code for training prescriptors with [NEAT](https://en.wikipedia.org/wiki/Neuroevolution_of_augmenting_topologies)
 
The instructions below assume that you are using a standard Python virtual environment, and `pip` for package 
management. Installations using other environments (such as `conda`) are outside the scope of these steps.

In order to run the examples locally:
1. Ensure your current working directory is the root folder of this repository (the same directory as this README 
resides in). The examples assume your working directory is set to the project root and all paths are relative to 
it.
1. Ensure your `PYTHONPATH` includes your current directory:
    ```shell script
    export PYTHONPATH="$(pwd):$PYTHONPATH"
    ```
1. Create a Python [virtual environment](https://docs.python.org/3/tutorial/venv.html)
1. Activate the virtual environment
1. Install the necessary requirements:
    ```shell script
    pip install -r requirements.txt --upgrade
    ```    
1. Start Jupyter services:
    ```shell script
    jupyter notebook
    ```
    This causes a browser window to launch
1.  Browse to and launch one of the examples (such as `linear`) and run through the steps in the associated 
notebook -- in the case of `v4c`, `predictor_train_no_region.ipynb`.
1. The result should be a trained predictor, and some predictions generated by running the predictor on test data. 
Details are in the notebooks.