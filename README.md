# Flight data exploration

## Dataset
Data is downloaded from [here](http://stat-computing.org/dataexpo/2009/the-data.html), from 2004 to 2008.  
  
I did data wrangling before I start data exploration. (Please refer to **wrangle_Flight.ipynb** under **data** folder)  
In original data, there are 29 features. I chose 13 of them and create one feature. Cleaned data is save in flight.csv.
There are 35,796,231 flight data in the dataset with 14 features. 7 features are numeric: **arrdelay_time, distance, carrier_delay,
weather_delay, nas_delay, security_delay, late_aircraft_delay**, and the other 7 features are categorical: **year, month, day_of_week, 
carrier, destination, cancellation_code, arrival_status**.  
arrival_status is defined by myself, including **Normal**, **Delay**, and **Cancelled**. The following is the definition of each status label.  
 - Normal : Arrival delay time is lower than 15 minutes.  
 - Delay : Arrival delay time is greater than 15 minutes.  
 - Cancelled : The flight is cancelled.

## Summary of findings
In data exploration, my interested features are arrival status and delay time.  
  
I plot on each individual features. Features that are delay time are highly right-skewed; hence, I use log transformation with them.  
  
In bivariate exploration, I plot correlation matrix at first. I found carrier delay time, NAS delay time, and late aircraft delay time 
are higher related with arrival delay time. I also plotted carrier, destination, time-based feature(year, month, day of week) with main 
features of interest. In June, July, December have more delay and longer delay time. In Winter, cancellation flights are more likely caused
by weather. Top3 destination with higher proportion of delayed flights are Newark Liberty International Airport(EWR), 
O'Hare International Airport(ORD), and Hartsfield-Jackson Atlanta International Airport(ATL); they also have longer delay time. 
Cancellation in each destination actually occupy little proportion.  
  
In mutivariate, I plot delay time versus monthe and year in order to see if the trend of monthly mean delay time are similar from year to year; actially it is. Finally, I plot delay time of each reason by carriers. For each carrier, main reason of delayed filghts are carrier ,late aircraft, or NAS. 

## Key insights for presentation
In presentation, I discuss on the US flights' delay and cancel from several aspect.
I focus on four problems:
 - What is the main reason of flights' delay and cancellation ?
 - How do carriers perform on delay and cancellation of flights ?
 - Does delay or cancellation relate to time ?
 - Which destinations have more delay or cancellation ? And which have longer delay time ?
