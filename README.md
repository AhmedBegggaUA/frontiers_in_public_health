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
