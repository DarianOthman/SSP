# Team 04 - Code Repository
## Flow of the Code
[Data Preprocessing](Data_Preprocessing.ipynb) -> [Data Analysis](Data_Analysis.Rmd) -> [Cluster Definition](SSP_project.ipynb) -> [Models](data%20analytics.Rmd) -> [Results](Results/)

## File Explanation and Related Data
**[Data Preprocessing](Data_Preprocessing.ipynb)**: This file takes as input the [extracted dataset](Data/data.csv) from CBS (Central Bureau for Statistics) and the [livability](Data/Leefbaarometer-scores%20buurten%202002-2022.csv) scores. The aim of this file is to select and normalize the relevant variables for our models. Namely, all the control variables are either retrieved or created and the distances are renamed for a better understanding. The outputs are the [distance](Data/distances.csv) and [variable](Data/normalized_variables.csv) files.
#### Variables Used in the models:
- Weighted Average Age: Created by taking the count of inhabitant in each bins of the age distribution.
- Standard Deviation Age: The standard deviation of the previous variable
- Prop 0-14, 15-24, 25-44, 45-64, 64+: The age distribution
- Prop University: Proportion of population which went to the university
- Worker: The proportion of population which is currently working, normalized (as an employee or independently)
- Prop Women: Proportion of women in the population, normalized
- Pop Density: Density of population, normalized
- Aid: Proportion of population which receives any kind of aid from the government, normalized (Unemployment, Pension, Sickness)
- Income: Income per capita of workers in the population, normalized
- Single Family Housing: The proportion of houses in which only one family lives
- Livability Score (Target Variable): The score out of 10 of how livable a neighbourhood is based on a survey from CBS

#### Commercial Spaces Used in the models:
- General Practicioner (GP)
- Hospital
- Supermarket
- Department Store
- Restaurant
- Day Care
- School

**[Data Analysis](Data_Analysis.Rmd)**: This file takes as input the [variable](Data/normalized_variables.csv) file and produces an analysis of the variable's colinearity through a matrix and its VIF values. The normality is also studied through a Q-Q plot.

**[X](Data_Analysis.Rmd)**: This collection of file builds upon the [data analysis](Data_Analysis.Rmd) to understand which variable has the biggesst influence on the livability score. The method used is called the log worth alogrithm.

**[Cluster Definition](Clusters.ipynb)**: This file takes as input the [variable](Data/normalized_variables.csv) file and creates clusters using different strategies (KMeans and DBscan). The [output](Data/df_normalized_clustering_output.csv) file is a collection of the cluster index to be used in the model.

**[Models](Models.Rmd)**: This file first combines in Excel the [variable](Data/normalized_variables.csv) file and the [cluster](Data/df_normalized_clustering_output.csv) file. Multiple regression models are used to determine the importance of each variable on the livability score. Concurently, the coefficients of the regressions are used as inputs for the final dashboard. An analysis of the model performance is also made in this file.

**[Results](Results/)**: Finally, all the outputs are presented in the folder [Results](Results/) for a better and clearer understanding.
