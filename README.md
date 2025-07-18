# World Happiness and Economic Indicators Exploration of the Post-COVID Pandemic Era
_By: Ryan Gallagher_

<img width="98" height="28" alt="image" src="https://github.com/user-attachments/assets/f8203909-a637-42b3-a8ad-2a597a504f39" />
<img width="139" height="28" alt="image" src="https://github.com/user-attachments/assets/c033112a-155b-49fe-8f46-666843d3ca9b" />
<img width="98" height="28" alt="image" src="https://github.com/user-attachments/assets/c18164e5-c630-493e-a987-0bb809f6a926" />
<img width="90" height="28" alt="image" src="https://github.com/user-attachments/assets/c2ba5563-945b-4036-9c1e-09ae5dfb6c70" />
<img width="109" height="28" alt="image" src="https://github.com/user-attachments/assets/9d38b637-730d-4377-b693-3449464f3408" />
<img width="84" height="28" alt="image" src="https://github.com/user-attachments/assets/b4da81c9-8880-402b-8c96-b5b3ef2a8648" />

## Overview
This project investigates the relationship between world happiness scores and an array of economic and social indicators from 2020 to 2023, the timeframe following the outbreak of the COVID-19 pandmenic. It employs data from the World Happiness Report and the World Bank’s World Development Indicators archive to analyze how indicators such as logged GDP per capita, healthcare expenditure, education expenditure, and internet usage influence national well-being. Such analysis is conducted in Python using a variety of machine learning and statistical techniques. Furthermore, results from such machine learning and statistical measures are stored in corresponding PDF files in the "Python Graphical Output" file of the repository. Moreover, the interactive Tableau story provides an interactive overview of the relationship between world happiness scores and such indicators and the performances of various machine learning models implemented in the study. 

## Python Component 

### Data Wrangling
In the data wrangling phase of this study, raw CSV files from the World Happiness Report and the World Bank are read into Pandas dataframes and a consistent structure is applied across all datasets. For the World Bank indicators, column names are standardized and reshaped to avoid naming conflicts during merging. Missing values are replaced with zeros for simplicity. The World Happiness data is similarly cleaned and merged by country name across all four years. Finally, the World Happiness and World Bank Indicator data are merged into a single master dataset to explore using various statistical and machine learning techniques in Pythob. Furthermore. a long-format version of the data is created to employ for Tableau usage. 

### Artificial Neural Networks 
#### Methodology
Artificial neural networks are employed to predict the happiness score for each year using the available economic and social indicators. The input features include Logged GDP per capita, social support, life expectancy, freedom of choice, generosity, perception of corruption, internet usage, education and healthcare expenditure, unemployment rate, and urban population percentage (in agglomerations of over 1 million people). The data is standardized before training a Multi-Layer Perceptron with two hidden layers. After training the network, predictions are made and compared against actual happiness scores. The mean absolute error is calculated for each year and the performance trends are visualized in a bar chart to evaluate the model’s effectiveness. Such results can be found in "ANN_Error_Graph.pdf" in the Python Graphical Output file of the repository. 

#### Results 
Per the results of the ANN mean absolute error bar chart, the model performance ranking (from most effective to least effective) is as follows: 2022 ANN model (MAE of 0.142), 2021 ANN model (MAE of 0.164), 2022 ANN model (MAE of 0.167), 2023 ANN model (MAE of 0.188). More extensive analysis of the artificial neural networks is conducted in Tableau. 

### Correlation Heatmap
#### Methodology
To explore the strength and direction of relationships between the happiness score and its respective social and economic indicators, a correlation matrix is computed for each year and visualized as a heatmap using  the Seaborn data visualization library. These heatmaps provide a quick glance of the strength of correlation between each indicator and happiness, revealing potential patterns or redundancies in the dataset. These correlation heatmaps can be found in "Correlation Heatmaps.pdf" of the "Python Graphical Input" file of the repository.

#### Results 
In a comprehensive overview of the corrleation heatmaps for each year, unemployment rate and perception of corruption harbor negative relationships with happiness score. Thus, it can be inferred that as unemployment rate and perception of corruption increase increase, happiness score decreases, which intuitively makes sense. Furthermore, per the correlation heatmaps, generosity has a negligible correlation with happiness score. Lastly, all other indicators (Logged GDP per capita, social support, healthy life expectancy, freedom to make life choices, internet users, education expenditure, healthcare expenditure, and population in urban areas) harbor positive correlations with happiness score. Thus, it can be inferred that as the rates of these indicators increase, happiness score increases, which intuitively makes sense. 

### KMeans Clustering and PCA
#### Methodology 
Foremost, the optimal number of clusters is determined for each year using the elbow method, which plots the inertia values (within-cluster sum of squares) across a range of possible cluster counts. Following analysis of the elbow charts, 4 clusters are selected as the optimal solution across all years. These elbow charts can be found in "KMeans PCA Elbow Charts.pdf" in the "Python Graphical Input" file of the repository. 

Once clustering is complete, Principal Component Analysis is applied to reduce the dimensionality of the dataset to two principal components, allowing for clear visualizations of the cluster structures. These PCA cluster charts can be found in "KMeans PCA Clusters.pdf" in the "Python Graphical Input" file of the repository. 

#### Results 
As aforemetioned, upon constructing the elbow charts for each year, it is evident that 4 clusters is optimal, as an "elbow" point occurs when k = 4. 

The results depicted in the cluster charts in "KMeans PCA Clusters.pdf" are stored in "KMeans_Clusters.csv" in the "Python Generated Data" file of the repository. Here, countries are clustered based on similarity in terms of happiness, social, and economic indicators.

### Linear Regression
#### Methodology
Linear regression models are built for each year to quantify the linear impact of each indicator on happiness scores. After standardizing the input data, a model is trained and its coefficients are extracted. Evaluation metrics such as the R-squared value and mean squared error are computed to assess model performance. Furthermore, the predictive capability of these is visualized using scatter plots that compare actual versus predicted happiness scores, thus assessing model accuracy. These scatter plots can be found in "Linear Regression Graphs.pdf" of the "Python Graphical Input" file of the repository. 

#### Results 
In the linear regression graphs, the predictive capability of the linear regression models is measured in terms of how far the data points deviate from the identity line, which indicates a "perfect fit." Based on the results of the graphs, it is evident that the 2023 linear regression model harbors the best performance while the 2020 linear regression model performs the worst. More extensive analysis of the linear regression models is conducted in Tableau. 

### Random Forests
#### Methodology
To capture non-linear relationships and interaction effects among variables, Random Forest regression models are trained for each year. This ensemble learning method aggregates predictions from multiple decision trees and outputs a ranked list of feature importances based on their contribution to reducing error in the model. Furthermore, the importance scores are visualized in horizontal bar plots. These plots can be found in "Random Forest Importances.pdf" in the Python Graphical Output file. 

#### Results
In the Random Forest importances bar charts, it is evident that social support is the most significant factor contributing to happiness each year by an overwhelming margin. On a similar note, it is clear that logged GDP per capita is the second most important factor contributing to happiness. Other significant factors include freedom to make life choices, healthy life expectancy, and internet users. Additional analysis of the relationship between happiness score and various indicators is conducted in Tableau, using these findings as a basis. 

## Tableau Component

### Overview 
<img width="1920" height="981" alt="Screenshot 2025-07-14 125604" src="https://github.com/user-attachments/assets/1aaf9340-ea50-47e5-81f5-23a3baa7d2c3" />

In the Overview dashboard, a chloropleth map is employed to show the happiness score in countries where metrics were obtained. A page is assigned to each year to visualize display how happiness scores changed from 2020- 2023. Based on the chloropleth map, it is evident that the highest rates of happiness reside in North America, Australia, and the United Kingdom. Furthermore, KPI cards are displayed below to highlight key takeways. For instance, the average world happiness score from 2020-2023 is 5.69. Furthermore, Finland is the happiest country while China is the country with the most growth in happiness score, on average. 



### Country Profile 
<img width="1920" height="975" alt="Screenshot 2025-07-14 133651" src="https://github.com/user-attachments/assets/4ecf3414-a123-4033-a834-61f1b1f68da8" />

The Country Profile dashboard displays two line charts: The first displays happiness score each year while the other displays the values of social and economic trends each year. Moreover, KPI cards are displayed below the line charts to state the value of each social, economic, and happiness feature for a selected year. Lastly, each dashboard element is adjusted based on the country selection of choice. 



### Top/Bottom 10 Countries: Average Happiness Score
<img width="1920" height="1001" alt="Screenshot 2025-07-14 134750" src="https://github.com/user-attachments/assets/c2e08d3c-e308-4107-9183-a2c9743e41cb" />

The Top/Bottom 10 Countries: Average Happiness Score dashboard displays two bar charts: The first displays the top 10 countries by happiness score and the second displays the bottom 10 countries by happiness score. Based on the bar chart, it is evident that the happiest country (by happiness score) is Finland while the least happy county is Afghanistan. 



### Happiness Score v. Various Indicators 
<img width="1920" height="989" alt="Screenshot 2025-07-14 125634" src="https://github.com/user-attachments/assets/6d271044-1659-4ec3-9767-703a7c7b0389" />

In the Happiness Score v. Various Indicators dashboard, four scatter plots are generated to help visualize correlation strengths between average happiness score and average social support (R^2 value of 0.67), average logged GDP per capita (R^2 of 0.69), average healthy life expectancy (R^2 of 0.62), and average internet users (R^2 of 0.54). These features were chosen based on the general highest importance ratings obtained from the Random Forest bar charts during Python analysis. 



### ANN Performance 
<img width="1920" height="981" alt="Screenshot 2025-07-14 125641" src="https://github.com/user-attachments/assets/f04d3b88-e048-45c2-9c67-bfb8fdd963d6" />

The ANN Performance dashboard displays two bar charts: The first displays the average mean absolute error values each year and the second displays actual vs. predicted happiness scores for a given country in a given year. Two dropdown filters are employed allowing the user to adjust the second bar chart for a given country in a given year. 


 
### Linear Regression Results
<img width="1920" height="992" alt="Screenshot 2025-07-14 142131" src="https://github.com/user-attachments/assets/47fd2b8f-4902-4114-abb1-c373bc93d5a7" />

In the Linear Regression Results dashboard, multiple elements are depicted to display relevant findings. 

Foremost, the Linear Regression: Model Performance Over Time bar chart displays the performances of each model based on average R^2 value each year. In the context of this study, the R^2 value quantifies the extent to which the variation in happiness score can be explained by the array of social and economic factors. Based on the bar chart, it is evident that the 2020 linear regression model performed the worst while the 2023 linear regression model performed the best. Since the range of R^2 values for the linear regression lies between (0.80, 0.86), it is evident that the social and economic indicators explain a significant proportion of variability in happiness score.  

Next, the Linear Regression: Values of Coefficients Over Time display changes in the value of coefficients corresponding to each social and economic indicator each year. Users are allowed to select as many indicators as they wish from the dropdown menu for graphical display. 

Lastly, the Linear Regression: Coefficient Highlight Table displays the value of each coefficient corresponding to each social and economic indicator each year. Furthermore, each coefficient value is color coded to help visualize its magnitude and direction. 

## Dictionary
- **Happiness score:** A composite measure representing the overall subjective well-being of a population, based on average answers to the Cantril ladder question, where respondents rate their current lives on a scale from 0 (worst possible) to 10 (best possible).
- **Logged GDP per capita:** The natural logarithm of the gross domestic product (GDP) per capita (in purchasing power parity, PPP, terms), used as a measure of the material standard of living.
- **Social support:** The national average of responses to the Gallup World Poll question: “If you were in trouble, do you have relatives or friends you can count on to help you whenever you need them, or not?” Hence, reflecting perceived support systems.
- **Healthy life expectancy:** The average number of years that a person can expect to live in good health, based on data from the World Health Organization. It reflects both quantity and quality of life.
- **Freedom to make life choices:** The average national response to the Gallup World Poll question: “Are you satisfied or dissatisfied with your freedom to choose what you do with your life?” Hence, measuring perceived autonomy.
- **Generosity:** The average response to the Gallup World Poll question: “Have you donated money to a charity in the past month?” Hence, serving as a proxy for prosocial behavior. 
- **Perceptions of corruption:** The national average of responses to two Gallup questions: “Is corruption widespread throughout the government or not?” and “Is corruption widespread within businesses or not?” Hence, measuring perceived integrity in public and private institutions. 
- **Internet Users:** The percentage of the population who have used the internet in the past 3 months, based on surveys or data from internet service providers (this includes access through any device, such as computers, mobile phones, or tablets). 
- **Education Expenditure:** Public spending on education expressed as a percentage of GDP. 
- **Healthcare Expenditure:** Public spending on healthcare expressed as a percentage of GDP. 
- **Unemployment Rate:** The share of the labor force that is without work but available for and actively seeking employment during a specified reference period (measured as a percentage of the total labor force). 
- **Population in Urban Areas:** The percentage of a country’s total population living in agglomerations of over 1 million people. 
