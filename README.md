
# Wrestling Medalists

### Table of Contents 
1. Introduction
2. Aim
3. Technology
3. Data
4. Preprocessing
5. Early EDA
6.  Final EDA
7. Modelling
8. Future Development

### Introduction

Analysis and prediction of athletes’ results are important tasks of sports science (sports psychology). In the short term, the solution of this problem allows  to determine the selection of more promising athletes and, in the long term, to optimise the athletes training.

### Aim

The project aims to predict wrestling medalists in world championships and to determine the features which are the most crucial ones for the prediction process. 

### Technology used

Python
Pandas
Numpy
Matplotlib
Seaborn
Scikit-Learn

### Data 
The data contain information about the sports careers of the freestyle and Greco-Roman male wrestlers who participated in the World Championships 2017, 2018. Before preprocessing, the information included such components: full name, date of birth, and international level results (name of competition, date, and rank).
The data of the results have been taken from the official site of the “United World Wrestling” (unitedworldwrestling.org).

The data were collected in the following format:
![01_raw_data_example](https://user-images.githubusercontent.com/82052288/161391241-e0ca2907-9a5f-4477-9748-48240d6c381c.jpg)

### Preprocessing
The DataFrame was created for the final analysis and modelling during preprocessing. Each row of the DataFrame contains the achievements of a particular athlete for the entire career period prior to participating in the World Championship.
A set of 16 features was compiled: age, relative age effect (RAE, including month/quarter/half year of birth), achievements in U18 competitions (participation/medalist/winner), achievements in U21 competitions (participation/medalist/winner) and achievements in continental and world championships until the moment of participation in the analysed competitions.
The final DataFrame looks like this:
![02_dataframe_example](https://user-images.githubusercontent.com/82052288/161391213-dd9dda0e-3f19-4d1e-abc5-16b4c6baab2c.jpg)
### Early EDA
At the first stage of the EDA, I identified outliers/errors/inaccuracies made at the stage of data preprocessing. They were removed (less than 1% of the sample).
### Final EDA
At the next stage of the analysis, I studied the relationship between the target and features. Histograms of targets were compiled; the first graph shows the dependence of the number of athletes on the place taken. It is worth noting that according to the new wrestling rules, there is no 4th place.

![01_rank](https://user-images.githubusercontent.com/82052288/164989636-77d7dac1-aaa0-4842-9eb0-28c62ab1937c.png)

There are two types of targets used in the work. The first type includes the categories of medalists (from the 1st to the 3rd places) and non-medalists (everyone else). The second type contains the categories of medalists (from the 1st to the 3rd places), middle ranks (from the 5th to the 10th ranks) and outsiders (everyone else). The main goal of the analysis is to show the differences between these categories in terms of the prediction features and to identify medal winners (highlighting the most important features for further predicting).

The age distribution of participants is presented by a histogram and a box plot. It can be seen that the age range for medalists is smaller, the mode corresponds to the age of 24 years (for non-medalists - 26 years), however, the medians for both categories are equal. 

![02_hist_box_age](https://user-images.githubusercontent.com/82052288/164992857-8629e8b4-2e3f-4390-ba3d-2762b416fbaf.png)

Relative age is an indicator that allows you to identify talents and predict the results. The diagram shows the number of athletes depending on the month of birth.

![03_dist_month_med](https://user-images.githubusercontent.com/82052288/164992861-8bbb1b18-2348-4bdd-83ec-eb331aff1ae7.png)

I built correlation matrices and visualised one of them as a heat map. The most significant correlations were found between win/success at the world/continental championships before the analysed competition and the predictor (max r = 0.3). However, it is not worth asserting a linear relationship between these indicators.

![04_matrix_corr_senior_m](https://user-images.githubusercontent.com/82052288/164992880-2327696d-2b34-453b-970b-7f4d911bdfb6.png)

A histogram of the number of athletes was constructed depending on the number of times that cadets participated in competitions for each category. Indicators of two and three participation times are higher for medalists than for non-medalists, as can be seen from the diagram.

![05_dist_count_cadet_part_m](https://user-images.githubusercontent.com/82052288/164992894-4730a32c-b961-4ae1-90a6-6aa03043dc54.png)




Percentage of medalists, %: 13.359528487229863
