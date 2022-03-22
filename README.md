# Linear Regression and Web Scraping Project

## Building a model to predict the popularity of Washington State’s Hiking Trails
By Nat Goodby

### Abstract
This project used a linear regression model to predict the popularity of hiking trails in Washington State. Coefficients from the regression can be used to better understand what characteristics of a trail tend to determine whether the trail is popular or not. This model can also be used on unseen data to identify undiscovered trails by identifying trails whose actual popularity is well below predicted popularity.   

### Design
The goal of the project was to produce a linear regression model to predict popularity of hiking trails to better understand what characteristics of a trail drive popularity. This information can be used by organizations looking to develop trails, allowing them to site and engineer trails that include popular characteristics. A secondary use of the model is to identify trails that are expected to be popular but have not yet been discovered by using the model on additional untested trails. 

### Data
The dataset contains information on 999 trails in Washington State, with 15 features for each, 3 of which are continuous integer values, and the rest are binary categorical variables. The data was scraped from https://www.alltrails.com/us/washington using Selenium to access the individual webpage of each trail (e.g. https://www.alltrails.com/trail/us/washington/rattlesnake-ledge). 

### Algorithms
Feature Engineering
1.	Create dummy variables based off of tags given to the trails.
2.	Log transform target.
3.	Standardize feature values using sklearn’s StandardScaler.

### Model
Basic linear regression, lasso, ridge, and elastic net regression models were tested. The elastic net regression was ultimately used for the model, as it had the strongest cross-validation performance. The dataset of 999 rows was split into 60/20/20 training/validation/test portions. Models were fit using the training data, then tested on the validation data. The 20% test data was used only at the very end to evaluate the performance of the finalized model. 

The final model had an adjusted R^2 value of 0.46 on the training data and 0.42 on the test data, with a mean absolute error of 928 (hikers). 

### Tools
- BeautifulSoup and Selenium for scraping data from the web
- Numpy and Pandas for data manipulation
- Scikit-learn for modeling
- Matplotlib and Seaborn for plotting
