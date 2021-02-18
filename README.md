# Training of machine learning models for COVID-19 dataset
# Installation:
# Requirements:
- Anaconda
- Python 3.5
- Numpy
- Scipy
- Sci-kit learn
- Pandas
- matplotlib

# Models are trained based on two output parameters
- Case Fatality Ratio (CFR)
- CFR = Cumulative number of death / Cumulative number of cases

- COVID-19 Spreading Ratio (CSR)
- CSR = Cumulative number of cases / Total population

# Data collection strategy
- Data are collected from 57 locations from all over the world
- We have divided the locations into 5 categories where the locations in each category have the similar density of 65+ aged population.  
- Distribution of population density over 65+ aged people: 
![pop_65+](Results/Figures/Pop_65+_category.png?raw=true "Title")

# Input dataset:
- We have total 22 input features in the dataset.
- Input features are chosen based on environmental, biological, pollution, and demographical factors.
- Some input parameters influence CFR, some of them influence CSR and some have an impact on both CFR and CSR. 

# Input features dictates CFR:
- Population density of 65 or older people 
- Vitamin A deficiency 
- Vitamin D deficiency 
- Health care quality and access index
- Pollutant PM2.5 particle 
- Anemia 
- AB+ 
- AB-
- A+
- A- 
- B+ 
- B- 
- O+ 
- O- 

# Input features dictates CSR:
- Solar radiation
- Daily Temperature 
- Precipitation
- Population density
- Average Wind speed
- Relative humidity
- Stringency index
- UV index

# Input features dictates both CFR and CSR:
- Pollutant PM2.5 particle 

# Methodology:
- To train the input dataset, Artificial Neural Netwrok is used for regression.
- GridSearch technique is used to choose the hyperparameters, activation function, solver, and number and the size of hidden layers. 
- Four hidden layers are used to train the model with the sizes of 22, 20, 10, 5. 
- A regularization parameter alpha is used to prevent the trained model from overfitting. 
- Non-linear activation function (Relu) is used to fit the non-linear dataset.
- Solver Adam is used to handle the noisy dataset. 

# Results:
- For CFR: 
- Training Error (MAE): 0.07686056937917364
- Testing Error (MAE): 0.08729698595622458

- For CSR:
- Training Error (MAE): 0.06867944664395645
- Testing Error (MAE): 0.11463206800503989

# Figures:
# Training Convergence [CFR]: 
![TrainConvg](Results/Figures/CFRLossVal.png?raw=true "Title")
# Training Convergence [CSR]: 
![TrainConvgCSR](Results/Figures/CSRLossVal.png?raw=true "Title")
# Parameter correlation: 
![Corr](Results/Figures/CorrCoefficient.png?raw=true "Title")
