# Flights Revenue and Load Factor Analysis
Since I’ve taken many flights in my life to Dublin, in this project, we aim to analyze the revenue performance of 4 flights from Dublin compared to the competition.

We consider factors such as fares, revenues, competition fares, and load factors (how full the plane is) over time until departure.




## 1. Flights performance at departure date  

Creating pivot tables and visualizing with excel we can see at departure date that:

- Flight FR101 contributes the least on revenue (5%) and it also has the lowest Load Factor (plane only half full) 
- Flight FR102 ranks third in revenue generation at 20%, yet it boasts the highest load factor at 104%, surpassing full capacity
- Flight FR103 generates the highest revenue, accounting for almost 50%, while ranking third in load factor.
- Flight FR104 ranks second in both load factor and revenue


![image](https://github.com/user-attachments/assets/13e78599-7354-4d31-858f-0310d10fc3d0)

NB Performing a check on official data we understand that usually Load Factor should be over 90% to keep the flight profitable
https://www.statista.com/statistics/1126148/ryanair-passenger-load-factor/#:~:text=In%20the%20financial%20year%20ending,million%20passengers%20on%20its%20flights.





## 3. Overview of Pricing Strategies Adopted
Su Excel possiamo plottare l'andamento delle fares e del load factor across time till departure, confronting our fares to the competition ones.
Da questo grafico possiamo dedurre che tipo di volo erano e la strategia adottata

FR101: The fares model could be too sensitive to Load Factor, starting to increase fares as soon as there is a Lf increase (27 dbd) even if we are only at 10% of LF, not increasing prices immediately could have avoided these cycles leading to higher LF.
We can see that there is amrgin with the competition fares  and infact we have to evaluate if is it possible to icnrease them even with low LF (relationship Fares-LF in this flight could be  weak)

FR102: The fare model is too indifferent to LF, taking the opposite approach. Fares are lowered to boost LF, leading to a sharp increase only in the week before departure. In the middle section we could have higher fares. (How to estimate loss)
 
FR103:Is the only flight in which fares are lowered at the end, we have to remember that LF started alreadya t 60% ,We might have achieved better results by keeping prices higher especially at the end.
 
FR104: Fares adjustments seem correct; the spike creates a plateau. However, the drop in the last week, as we’ll see, could have been avoided (60% decrease in fares that then icnrease again just for getting one more customer)


![image](https://github.com/user-attachments/assets/f0238318-f0cf-40ff-9c66-78fd3fba5901)


## 4. Possible Improvement strategy

When could we have raised fares? 
- If customers are indifferent to fares changes (Elasticity of the prices around 0 or positive)
- If we have margin with respect to competition fares
- If we have strong seasonality (ex.Sunday)

Oltre all' elasticità calcolata in Excel abbiamo bisogno anche di un'analisi piu statistica performata su Rstudio,
per vedere se l'effetto

- The Fares’ effect on number of daily bookings
  Daily Bookings Number = β Fare + β DaysUntillDeparture + β Weekday 

![image](https://github.com/user-attachments/assets/581d260f-3220-48d5-9833-24da7d9a27ac)

- The Fares’ effect on daily Revenues:
      If we can increase fares without reducing bookings we still have to check if this reduces revenues
      (higher fares could reduce secondary revenues like additional baggage purchases)
Daily Revenues=βFare+βDUD+βWeekday
![image](https://github.com/user-attachments/assets/44be63f5-ee9e-4e90-bdaf-8fba211facc0)






![image](https://github.com/user-attachments/assets/993c54d7-c928-4fe7-a39e-80ba823a3f22)




6. Conclusions!
