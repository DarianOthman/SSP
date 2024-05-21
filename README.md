# Team 04 - Code Repository
## Flow of the Code
[Data Preprocessing](Data_Preprocessing.ipynb) -> [Data Analysis](Data_Analysis.Rmd) -> [Cluster Definition](SSP_project.ipynb) -> [Models](data%20analytics.Rmd) ->

## File Explanation and Related Data
**[Data Preprocessing](Data_Preprocessing.ipynb)**: This file takes into input the [extracted dataset](Data/data.csv) from CBS (Central Bureau for Statistics) and the [livability](Data/Leefbaarometer-scores%20buurten%202002-2022.csv) scores. The aim of this file is to select and normalize the relevant variables for our models. Namely, all the control variables are either retrieved or created and the distances are renamed for a better understanding. The outputs are the [distance](Data/distances.csv) and [variable](Data/normalized_variables.csv) files.

**[Data Analysis](Data_Analysis.Rmd)**: This file takes into input the [variable](Data/normalized_variables.csv) file and produces an analysis of the variable's colinearity through a matrix and its VIF values. The normality is also studied through a Q-Q plot.

**[X](Data_Analysis.Rmd)**: This collection of file builds upon the **[data analysis](Data_Analysis.Rmd)** to understand which variable has the biggesst influence on the livability score. The method used is called the log worth alogrithm.

**[Cluster Definition](SSP_project.ipynb)**: This file takes into input the [variable](Data/normalized_variables.csv) file and creates clusters using different strategies (KMeans and DBscan). The [Data/df_normalized_clustering_output.csv]() is a collection of the cluster index to be used in the model.

**[Models](data%20analytics.Rmd)**: This file first combines in Excel the [variable](Data/normalized_variables.csv) file and the [cluster]() file. Multiple regression models are used to determine the importance of each variable on the livability score. Concurently, the coefficients of the regressions are used as inputs for the final dashboard. An analysis of the model performance is also made in this file.
