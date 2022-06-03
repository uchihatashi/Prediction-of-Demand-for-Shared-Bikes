# Prediction of Demand for Shared Bikes
In this project I have build a multiple linear regression model for the prediction of demand for shared bikes.
And to understand the factors on which the demand for these shared bikes depends. Specifically, BoomBikes want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

- Which variables are significant in predicting the demand for shared bikes.
- How well those variables describe the bike demands


## Problem Statement
A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider **BoomBikes** has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state. 

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

- Which variables are significant in predicting the demand for shared bikes.
- How well those variables describe the bike demands

Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors. 


### Business Goal:
You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 

### Data Preparation:

1. You can observe in the dataset that some of the variables like 'weathersit' and 'season' have values as 1, 2, 3, 4 which have specific labels associated with them (as can be seen in the data dictionary). These numeric values associated with the labels may indicate that there is some order to them - which is actually not the case (Check the data dictionary and think why). So, it is advisable to convert such feature values into categorical string values before proceeding with model building. Please refer the data dictionary to get a better understanding of all the independent variables.

2. You might notice the column 'yr' with two values 0 and 1 indicating the years 2018 and 2019 respectively. At the first instinct, you might think it is a good idea to drop this column as it only has two values so it might not be a value-add to the model. But in reality, since these bike-sharing systems are slowly gaining popularity, the demand for these bikes is increasing every year proving that the column 'yr' might be a good variable for prediction. So think twice before dropping it. 

### Model Building

In the dataset provided, you will notice that there are three columns named 'casual', 'registered', and 'cnt'. The variable 'casual' indicates the number casual users who have made a rental. The variable 'registered' on the other hand shows the total number of registered users who have made a booking on a given day. Finally, the 'cnt' variable indicates the total number of bike rentals, including both casual and registered. The model should be built taking this 'cnt' as the target variable.

### Model Evaluation:
Model evaluation is done using the R-squared score on the test set.

### Structure:

	-- data
	 	-- Readme.txt
	 	-- day.csv
	 -- Assingment - Bike Sharing.ipynb
	 -- Subjective Questions and Answers.pdf


**The equation of best fitted surface based on final model is:**

    cnt = 0.289559 + (0.235183 x yr) + (0.400700 x temp) + (-0.155351 x windspeed) + 
          (-0.291683 x "Light Rain + Scattered clouds") + (-0.079767 x "Mist + Broken clouds") + 
          (-0.106410 x spring) + (0.064733 x winter) + (-0.052012 x Dec) + (-0.056864 x Jan) + 
          (-0.063100 x Jul) + (-0.056717 x Nov) + (0.049740 x Sep)

1. `const`: `0.289559`
    - This means, when the absence of other predictor variables, the bike rental can still be increased by a `0.289559` unit.
2. `yr` : `0.235183`
    - This means, when the absence of other predictor variables, the bike rental can still be increased by a `0.235183` unit.
3. `temp ` : `0.400700`
    - This means, when the absence of other predictor variables, the bike rental can still be increased by a `0.400700` unit.
4. `windspeed ` : `-0.155351`
    - This means, when the absence of other predictor variables, the bike rental can still be deceased by a `0.155351` unit.
5. `Light Rain + Scattered clouds` : `-0.291683` 
    - This means, when the absence of other predictor variables, the bike rental can still be decreased by a ` 0.291683` unit.
6. `Mist + Broken clouds` : `-0.079767` 
    - This means, when the absence of other predictor variables, the bike rental can still be increased by a `0.079767` unit.
7. `spring ` : `-0.106410`
    - This means, when the absence of other predictor variables, the bike rental can still be decreased by a `0.106410` unit.
8. `winter ` : `0.064733`
    - This means, when the absence of other predictor variables, the bike rental can still be increased by a `0.064733` unit.
9. `Dec` : `-0.052012`
    - This means, when the absence of other predictor variables, the bike rental can still be decreased by a `0.052012` unit.
10. `Jan` : `-0.056864`
    - This means, when the absence of other predictor variables, the bike rental can still be decreased by a `0.056864` unit.
11. `Jul`: `-0.063100`
    - This means, when the absence of other predictor variables, the bike rental can still be decreased by a `0.063100` unit.
12. `Nov` : `-0.056717`     
    - This means, when the absence of other predictor variables, the bike rental can still be decreased by a `0.056717` unit.
13. `Sep` : `0.049740`:
    - This means, when the absence of other predictor variables, the bike rental can still be increased by a `0.049740` unit.
****


## Final Result:

1. **R-square value:**
	-  **For train:**
		- R-squared: 0.834
		- Adj. R-squared: 0.830
	- **For test:**
		- R-squared: 0.816
		- Adj. R-squared: 0.804
	- Difference between train and test R-square value is 0.834-0.816 = 0.018 (1.8%)
	- Difference between train and test Adj. R-squared value is 0.830-0.804 = 0.026 (2.6%)


2. `Temperature` shows the highest coefficient of around 0.400700, which means when the `temp` is increased by one unit, the rental bike increases by 0.400700
3. `Light Rain + Scattered clouds` shows a negative coefficient of around 0.291683; this means when `this variable` increases by one unit, the rental bike will decrease by 0.291683.
4. `yr` shows the 2nd  highest coefficient of around 0.235183, which means when the `yr` is increased by one unit, the rental bike increases by 0.235183
5. `windspeed` shows a second highest negative coefficient of around 0.155351; this means when `windspeed` variable increases by one unit, the rental bike will decrease by 0.155351.
6. `spring` shows a third highest negative coefficient of around 0.106410; this means when `spring` variable increases by one unit, the rental bike will decrease by 0.106410.
****

## Business Goals:
1. The `temperature` is highly correlated and having a high coefficient with `cnt,` but we know from `EDA` that if the temperature goes higher than 35, we see fewer bikes rented. So they should know that when the temperature is between `20-35`, there will be more people renting bikes. 
2. If the weather is like `Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds,` then people tend to rent bikes less. 
3. The windspeed shows a negative coefficient with `cnt,` but we need to know when wind speed is between `5-20` then people rent more bikes through EDA, but we have to know that wind speed above will always affect.
4. `spring` shows a negative coefficient with `cnt,` so we should offer more in `spring.`
5. The business  has increased from 2018 to 2019 so that's why it show high coefficient with `cnt`.
6. People prefer to rent a bike between May to October.
7. And gradually decrease from December to Feb.

