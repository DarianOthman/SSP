# Team 04 - Code Repository
## Flow of the Code
[Data Preprocessing](Data_Preprocessing.ipynb) -> [Data Analysis](Data_Analysis.Rmd) -> [Cluster Definition](SSP_project.ipynb) -> [Models](data%20analytics.Rmd) ->

## File Explanation and Related Data
[Data Preprocessing](Data_Preprocessing.ipynb): This file takes into input the [extracted dataset](Data/data.csv) from CBS (Central Bureau for Statistics) and the [livability](Data/Leefbaarometer-scores%20buurten%202002-2022.csv) scores. The aim of this file is to select and normalize the relevant variables for our models. Namely, all the control variables are either retrieved or created and the distances are renamed for a better understanding. The outputs are the [distance](Data/distances.csv) and [variable](Data/normalized_variables.csv) files.
