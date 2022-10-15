# neuefische-bootcamp-eda-project

## Project - Data Analysis<br>
This project is a part of the Neuefische data analytics bootcamp and centered around exploratory data analysis (EDA) techniques and statistical analysis.

### Objective: Business Understanding and extracting information from customer briefing

A Muesli distribution company has approached you to help them understand their delivery process. They want to develop KPIs to help them keep track of the health of their business in order to improve the service they offer their customers.

The warehouse manager described the workflow as follows: Order received (Day 1) - order processed in warehouse and made ready to ship (normally 2 days) - order leaves warehouse in truck following day - order delivered to customer (handled by logistics company).

The company has provided a list of their transactions over the course of the past years. They have full data on Order Date and the ‘On Truck Scan’ date but have limited visibility of what happens in between. They have on occasion sent some interns into the warehouse to record the ‘Ready to Ship’ date for as many orders as they could. The warehouse manager says they have not changed their processes much in the past year so they think it should be a good estimate.

Customers can send orders every day but the warehouse only works Monday to Friday so any orders received on the weekends wait until Monday to be actioned.

Trucks Leave the warehouse on Mondays, Wednesdays and Fridays. Orders leave on trucks the day after they are made ready for shipping (or two days later if there is no truck). Customers can pay for Express Processing that means the orders leave on the truck the day the order is ready for shipping.

The logistics company has said they have on average 3 day delivery times to all locations. They transport goods on weekends but only deliver to customers from their local distribution centers on weekdays. The Muesli company has some data about exact delivery dates for a number of shipments that was gathered via marketing promotions they ran where customers scanned a QR code on the package in order to register for a prize. (We assume customers always scanned the code on the day of arrival).


### KPI's:
- On-time-deliveries: how long does it take from ordering the muesli until it arrives?
  - Warehouse (Average 2 days - is it true that the warehouse has the order ready after 2 days?) → Needs "Order Date" and "Ready to Ship"<br>Formula: "InternData Study_Ready to Ship date" minus "Order Date"
  - Logistic company (Average the 3 days - Is it true, that the delivery company only needs 3 days on average?) → Needs "On Truck Scan" and "Arrival Scan"<br>Formula: "Campaign Data_Arrival Scan Date" minus "Order Process Data_On Truck Scan Date"
  - Delivery Time for the different Ship-Modes (First, Second, Standard - Class) → Needs "On Truck Scan" and "Arrival Scan" dependent on Ship-Mode<br>Formula: "Arrival Scan" minus "On Truck Scan" for every 3(2!) Ship-Modes
  - Complete delivery time → Needs "Order Date" and "Arrival Scan"<br>Formula: "Campaign Data_Arrival Scan Date minus Order Date"
- Process time to Warehouse: Is there a difference between the "Origin Channel"? → Needs "Origin Channel", "Order Date" and "Ready to Ship"
