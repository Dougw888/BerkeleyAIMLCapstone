### Predicting wood, charcoal, and other solid fuels for cooking in Mexican households

**Douglas Watts**

#### Executive summary
For Mexican households, simple decision tree modeling can predict whether a household uses wood, charcoal, or other burned solid fuel for their main cooking fuel with an accuracy of 88%. The most important features that predict a households cooking fuel are the presence of an outdoor kitchen, presence of public services (such as trash collection), the presence of indigenous speakers in the house, and household income. Further investigation will focus on expanding which models to use (e.g., logistic, KNN, ensemble techniques) for classification prediction to increase accuracy while also layering in additional data on rural vs. urban, other household information, and specificity on indigenous languages spoken.

#### Rationale
Currently, 13% of homes in Mexico cook with wood or charcoal as their primary fuel source, with 39% of homes in the four poorest states doing so. And despite being in the top 5 of GDP per capita in Latin America, Mexico trails most of the South and Central American countries in access to clean cooking fuels. What can we learn about areas in Mexico that have high use of wood or charcoal cooking that could predict which homes use wood or charcoal as their primary cooking fuel and why they haven't switched to gas or electric? Is it cultural? Economic? Something else? This is an important question as there are major health, climate, and deforestation implications for continuing to cook with biofuels.

#### Research Question
Are there any determinants that will predict whether a house uses wood, charcoal, coal or other solid biofuels for cooking in the home? This could be income, cultural, geography, etc.

#### Data Sources
IPUMS International as the source of Mexico 2020 Census data

#### Methodology
In the initial findings, I am using simple decision trees to set a baseline accuracy for using certain demographic data on a household level. I will then test other modeling methods against this baseline including random forests, KNN, SVM, and logistic regression. I am also determining which factors are most important for modeling and including or eliminating overlapping demographic data that doesn't have an impact on model accuracy while improving interpretability and usefulness of the model.

#### Results
My initial modeling had a test accuracy of 88% with a training accuracy of 88%. The model initially found that the most important factors were the kitchen type (e.g., indoor vs. outdoor kitchen), the presence of public services like trash collection and sewer, the presence of an indigenous language spoken at home, and income.

#### Next steps
Next I will be expanding the modeling to enhance prediction accuracy and interpretability. This means increasing granularity of indigenous speaker data, adding new data like presence of a vehicle or air conditioning, as well as population density (rural vs. urban).

#### Outline of project

- [Jupyter Notebook](https://github.com/Dougw888/BerkeleyAIMLCapstone/blob/main/Capstone_v2.ipynb)
- [IPUMS Data](https://github.com/Dougw888/BerkeleyAIMLCapstone/blob/main/Data/ipumsi_00003.csv.gz)


##### Contact and Further Information
Anyone interested in this project can reach out to me at dougwatts@berkeley.edu