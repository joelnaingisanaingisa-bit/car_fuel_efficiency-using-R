# car_fuel_efficiency-using-R
### CAR FUEL  EFFICENCY ANALYSIS USING R
# Problem statement
Investigate the relationship between car weight and fuel efficiency using the car_fuel_efficiency_32 dataset.
# By: 
 How does car weight (wt) affect fuel efficiency (mpg)?
What is the average fuel efficiency of the cars in the dataset?
Can we visualize and model the relationship between weight and mileage?
## Approach:
# Loaded and explored the dataset.
#load $ inspect csv file
<- read.csv("C:/Users/Public/car_fuel_efficiency_32.csv", stringsAsFactors=TRUE)
print(car_fuel_efficiency_32)
car_fuel_efficiency_32 



## Calculated summary statistics for fuel efficiency and weight.
#summery $ descriptive statistics
summary(car_fuel_efficiency_32)        # Descriptive statistics
dim(car_fuel_efficiency_32)            # Rows and columns
nrow(car_fuel_efficiency_32)           # Number of rows
ncol(car_fuel_efficiency_32)           # Number of columns
mean(car_fuel_efficiency_32$mpg)       #avg  fuel efficiency

relationship
#relationship btn wt $ mpg using ggplot scatter plot
library(ggplot2)

ggplot(car_fuel_efficiency_32, aes(x=mpg, y=weight, colour = "steelblue"))+
    geom_point(size=4, alpha=0.8)
labs(title="mpg vs weight", x="mpg", y="weight" )+
  theme_minimal()

  


## Visualized the relationship using a scatter plot with a regression line and Built a linear regression model to quantify the relationship.
 
##Linear regression model pridicted by weight using mpg
model<-lm(weight~mpg , data=car_fuel_efficiency_32)
summary(model)

#Ploting the regressio model line
ggplot(data=car_fuel_efficiency_32, aes(x=mpg, y=weight))+
  geom_point(size=4, alpha=0.8, color="blue")+
  geom_smooth(method = "lm", color="red", se=TRUE)
labs(title="Regression analysis of mpg vs weight", x="mpg", y="weight" )+
  theme_minimal()

## Model interpretation.
The regression analysis shows a negative relationship between car weight and fuel efficiency.
 This means that as car weight increases, miles per gallon (MPG) decreases. Therefore, heavier cars tend to consume more fuel than lighter cars.”



## Key findings:

There is a strong negative correlation between car weight and fuel efficiency.
As car weight increases, miles per gallon tends to decrease.
The linear regression model confirms that weight is a significant predictor of fuel efficiency.


