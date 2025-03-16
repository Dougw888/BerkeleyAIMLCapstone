### Predicting wood, charcoal, and other solid fuels for cooking in Mexican households

**Douglas Watts**

#### Executive summary
For Mexican households, random forests or logistic regression can predict whether a household uses wood, charcoal, or other burned solid fuel for their main cooking fuel with an accuracy of 89%. The most important features that predict a households cooking fuel change based on the model used but generally revolve around the presence of an outdoor kitchen, presence of public services (such as trash collection), the presence of indigenous speakers in the house, and household income. In general, income is related to public services and conveniences (e.g., air conditioning) and if we strip away all other variables then household income per person and indigenous status are the top predictors of wood use, with an accuracy of 85%.

#### Rationale
Currently, 13% of homes in Mexico cook with wood or charcoal as their primary fuel source, with 39% of homes in the four poorest states doing so. And despite being in the top 5 of GDP per capita in Latin America, Mexico trails most of the South and Central American countries in access to clean cooking fuels. What can we learn about areas in Mexico that have high use of wood or charcoal cooking that could predict which homes use wood or charcoal as their primary cooking fuel and why they haven't switched to gas or electric? Is it cultural? Economic? Something else? This is an important question as there are major health, climate, and deforestation implications for continuing to cook with biofuels.

#### Research Question
Are there any determinants that will predict whether a house uses wood, charcoal, coal or other solid biofuels for cooking in the home? This could be income, cultural, geography, etc.

#### Data Sources
IPUMS International as the source of Mexico 2020 Census data

#### Methodology
To clean the data I had to find outliers, eliminate unknown and other values, and reduce bias from potential data input errors (such as very low income $1-100/year exhibiting similar characteristics to houses making $60-100K per year). I also used income per person as a feature, vs. household income because I thought it was more accurate of a method for understanding purchasing power for various household features (e.g., trash collection). 

In the initial findings, I used simple decision trees to set a baseline accuracy for using certain demographic data on a household level. This was because they were fast to model on a large dataset and provided me with a fairly strong starting accuracy (87%). From there, I also tried multiple other models and ensemble models, including logistic regression (first and second degree polynomial), K nearest neighbors (KNN), support vector classification (SVC), and random forests, adaptive boosting (AdaBoost), and voting classifier using logistic regression, trees, and SVC. 

#### Results
My initial modeling had a test accuracy of 88% with a training accuracy of 89%. The model initially found that the most important factors were the kitchen type (e.g., indoor vs. outdoor kitchen), the presence of public services like trash collection and connected sewer system, the presence of an indigenous language spoken at home, and income. Based on the scatter plots below, it's clear there are relationships between income and public services (lower rates of trash collection, sewer connection, etc.), household characteristics (e.g., low income likely to have outdoor kitchen), population density (lower income in rural places), and indigenous language spoken at home (high rates of indigenous language have much lower income).

![Scatter plot for income vs. wood burning cooking](https://github.com/Dougw888/BerkeleyAIMLCapstone/blob/fa4abf70198a4ec7fbf98fcc7c4a4bb3331e6823/Plots/Wood_proportion_by_income.png)
![Scatter plot for outdoor kitchen vs. income](https://github.com/Dougw888/BerkeleyAIMLCapstone/blob/fa4abf70198a4ec7fbf98fcc7c4a4bb3331e6823/Plots/Outdoor_kitchen_by_income.png)
![Scatter plot for trash collection vs. income](https://github.com/Dougw888/BerkeleyAIMLCapstone/blob/fa4abf70198a4ec7fbf98fcc7c4a4bb3331e6823/Plots/Trash_collection_by_income.png)
 
With other models, I reached a maximum accuracy of 89%, through both 2nd degree logistic regression and random forests. What's interesting is these two models had different importance for different characteristics. In random forests, and trees in general, outdoor kitchens, trash collection, and indigenous language presence were more predictive than income (per person) whereas in logistic regression household income and population density were the largest coefficients and had the biggest impact on accuracy. 

What the results show is a combination of household income and living situation have the largest impact on whether you cook with wood. All other indicators are likely driven from those two pieces. While 90% of indigenous speaking homes cook with wood, a large portion of those are due to low incomes and because of low incomes, more likely to own a home that has an outdoor kitchen and therefore more likely to cook with wood because gas is more expensive. This is supported by other literature from research on gas use in Mexico, that homes that cook with wood, charcoal, or other biomaterials know that cooking with gas is healthier for the home, but are unable to purchase the equipment or afford the gas when biomaterial is more available or free. 

For the Mexican government to support healthier homes and cooking, there must be some incentive provided for homes to cook with gas. Communities that can't afford gas, like many indigenous communities in Mexico, need some way of accessing a healthier and better way of cooking. By providing the lowest income homes with gas at a competitive cost, time spent cooking by women will be reduced, health outcomes will improve, and local economies should be more productive. The first place to start is in homes that have indoor kitchens, since smoke inhalation would be particularly dangerous indoors. In these homes, trash collection and indigenous language are large indicators of whether wood cooking is done or not. Therefore, indigenous communities with homes that have indoor cooking would benefit the most from gas incentives.  

#### Next steps
It's still not entirely clear how much of wood cooking is related to economic vs. cultural. It is surely a majority economic based on the results, but there is still significant parts of Mexican cuisine and culture that use smoke as key flavor (mezcal, barbacoa, smoked chiles, etc.) which come from areas that use high proportions of wood cooking (Oaxaca, Yucatan, etc.), while there are other regions of Mexico that have high wood cooking content but don't exhibit much smoked foods and therefore rely on wood for cooking fuel due to economic reasons (e.g., Chiapas). There needs to be more granular focus on a state or region level to determine main causes for each region of Mexico for a more specific strategy on best ways to reduce wood based cooking without impact cultural aspects.

I’d also want to look at the data from the model predictions that are incorrect from the test data to see if there are any underlying trends. Perhaps this is where the cultural and societal use of wood for cooking is hidden. 

This work is important for both policy makers (in energy, public health, and economic development) as well as gas companies and appliance makers. Gas companies can provide cheaper options (e.g., smaller tank sizes, pick-up vs. delivery) or partner with appliance makers to install new appliances in homes that need them and expand the gas customer base and their revenue. These efforts can be focused on areas with indigenous communities and highest proportion of wood-based cooking to maximize conversion benefits.  

#### Outline of project

- [Jupyter Notebook](https://github.com/Dougw888/BerkeleyAIMLCapstone/blob/fa4abf70198a4ec7fbf98fcc7c4a4bb3331e6823/Capstone_v5.ipynb)
- [IPUMS Data for First Decision Tree Analysis](https://github.com/Dougw888/BerkeleyAIMLCapstone/blob/fa4abf70198a4ec7fbf98fcc7c4a4bb3331e6823/Data/ipumsi_00003.csv.gz)
- [IPUMS Data with increased detail on indigenous languages for more advanced modeling](https://github.com/Dougw888/BerkeleyAIMLCapstone/blob/fa4abf70198a4ec7fbf98fcc7c4a4bb3331e6823/Data/ipumsi_00006.csv.gz)
  
##### Contact and Further Information
Anyone interested in this project can reach out to me at dougwatts@berkeley.edu
