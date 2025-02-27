# Flights Revenue and Load Factor Analysis
Since I have taken many flights in my life to Dublin, in this project, we aim to analyse the revenue performance of 4 flights from Dublin compared to the competition.

We consider factors such as fares, revenues, competition fares, and load factors (how full the plane is) over time until departure.




## 1. Flights performance at departure date  

Creating pivot tables and visualizing with excel we can see at departure date that:

- Flight FR101 contributes the least on revenue (5%), and it also has the lowest Load Factor (plane only half full) 
- Flight FR102 ranks third in revenue generation at 20%, yet it boasts the highest load factor at 104%, surpassing full capacity
- Flight FR103 generates the highest revenue, accounting for almost 50%, while ranking third in load factor.
- Flight FR104 ranks second in both load factor and revenue


![image](https://github.com/user-attachments/assets/13e78599-7354-4d31-858f-0310d10fc3d0)

NB Performing a check on official data we understand that usually Load Factor should be over 90% to keep the flight profitable
https://www.statista.com/statistics/1126148/ryanair-passenger-load-factor/#:~:text=In%20the%20financial%20year%20ending,million%20passengers%20on%20its%20flights.





## 3. Overview of Pricing Strategies Adopted
In Excel, we can plot the trend of fares and load factor over time until departure, comparing our fares to those of the competition.
From these charts, we can infer the type of flight and the strategy adopted.
- FR101: The fares model could be too sensitive to Load Factor, starting to increase fares as soon as there is a LF increase (27 days before departure) even if we are only at 10% of LF, not increasing prices immediately could have avoided these cycles leading to higher LF.
We can see that there is margin with the competition fares  and indeed we must evaluate if is it possible to increase them even with low LF (relationship Fares-LF in this flight could be  weak)

- FR102: The fare model is too indifferent to LF, taking the opposite approach. Fares are lowered to boost LF, leading to a sharp increase only in the week before departure. In the middle section we could have higher fares. (How to estimate loss)
 
- FR103:Is the only flight in which fares are lowered at the end, we must remember that LF started already t 60% ,We might have achieved better results by keeping prices higher especially at the end.
 
- FR104: Fares adjustments seem correct; the spike creates a plateau. However, the drop in the last week, as we will see, could have been avoided (60% decrease in fares that then increase again just for getting one more customer)


![image](https://github.com/user-attachments/assets/f0238318-f0cf-40ff-9c66-78fd3fba5901)


## 4. Possible Improvement strategy

When could we have raised fares? 
- If customers are indifferent to fares changes (**Elasticity** of the prices around zero or positive)
- If we have margin with respect to competition fares
- If we have strong seasonality (ex. Sunday)

Besides the elasticity calculated in Excel, we also need to check if fares influence the number of daily bookings and if fares affect revenues. 

We can expect that increasing fares may reduce bookings, but raising fares could also lead customers to spend less on secondary services, potentially reducing revenues. 

Therefore, in RStudio we estimate the regressions parameters for:   

1. **The Fares’ effect on number of daily bookings**:     
  Daily Bookings Number = β Fare + β DaysUntillDeparture + β Weekday   
  (Here Fares have no significant effect on bookings) 

![image](https://github.com/user-attachments/assets/581d260f-3220-48d5-9833-24da7d9a27ac)

2. **The Fares’ effect on daily Revenues**:
 Daily Revenues=β Fare + β DUD + β Weekday    
 (Here fares have positive significant effect only for flight 101 e 102)
  
![image](https://github.com/user-attachments/assets/44be63f5-ee9e-4e90-bdaf-8fba211facc0)

**4. Conclusions!**

**Flight FR101**:
•	LF too low   
•	Elasticity strong variation, no seasonality   
•	High margins with competition    

LF is exceptionally low, and lowering fares should not lead to an increase in bookings. 
Increasing fares could increase revenues without lowering LF but this flight has an elevated risk to create a monetary loss.


**Flight FR102**:   
•	LF too high   
•	Scarce Elasticity   
•	Significant week seasonality   
•	High margins with competition in the middle of the period   

Fares should have been increased during the middle period, considering the weekdays with higher demand. 
This adjustment would have helped manage the high demand level, but scarce elasticity must be kept in mind   

      
**Flight FR103**:   
•	Good LF performance   
•	Scarce elasticity   
•	Margins with competition fares  at the end   
We should study whether the LF at 60% already at the beginning is recurring, if so, prices could be increased especially at the end. 


**Flight FR104**:
• Good LF performance   
• Scarce elasticity   
• Scarce margin with competition   
Efficiency is good, but the final drop in fares could have been avoided. Only one additional booking was gained from a 60% fare reduction,     
before fares were subsequently increased again. 



