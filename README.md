#  :pushpin: Sales Tracker System for LS Associates Group  #
This is a project based on MySQL to partially create the business database structure for all the gaming store branches of "LS Associate Group"

##	The Problem ##
"LS Associate Group" needs a chipper solution for their tracking and managing sales data system, they cannot afford their actual license.

## The Solution ##
Reform the DB structure creating a relational database system to track their sales using MySQL and afterward add the DB to azure SQL data container.

### Description ### 
 This application is meant to  `partially` monitor the data of a video game store franchise. It holds both logistic data useful for making financial decisions on a higher authority level, and information that can be used by retail workers for increased efficiency when helping customers.
 
 These data project was made in response to a client consulting program at `Mercantile Bank` designed to proportionate business intelligence guidance to loan holders and small business partners. 
 
 In this sense the code of `db_queries` was created in order to display a variety of usable techniques, and thus some of the queries are unrealistic or even slightly comedic in nature.

## Entity Relationship Diagram ##

 ![Alt text](https://github.com/labradorsabrina/LSGroup/blob/main/Model(LSGroup).jpg)


##	Field Description ##

### 1. Customers ###
Field | Description
----------------|-------------
Cust_id | A unique id for every registered customer. This application will only monitor purchases made from registered customers.
Cust_gender | Used to deduce the title of a customer when addressing them.
Cust_address | Used for the competition query. Can be used for statistical analyses when it comes to regional productivity and allocation of resources.
Region | An extension of the address, kept in a separate field so it can be easily accessed for large scale statistics.
Cust_class | The class of the customer, customers could change class based on activity and commitment to the brand. Will be later used to provide discounts for local purchases.
Cust_card_code | Some of the customers have opted to sign in for a card. The card collects credits based on a number of things like purchases or store events.
Prime | Prime is a paid service that a customer may choose to sign on, that will remove the urgency fees on online orders. Other bonuses like extra credits can be awarded to prime members.

### 2. Payment Method ###

Field | Description
------|-----------
Card_id | A unique card id, associated with Cust_card_code.
Credit | The number of credits in any given card.
Card_status | Some clients might not opt to renew their cards and they will be rendered inactive. The credits will count for the rest of the year, but the customer will not be eligible for the grand prize unless he reactivates the card before a certain deadline.
Activation/Expiration dates | Useful to let the customer know about the status of their card.

### 3. Products *Games* ###

Field | Description
------------------|----------------------
Prod_id | Important for tracking and storage. Could also be used to gather statistical data about the performance of a specific product.
Prod_name | The title of the product. Can be used for informative purposes.
Genre | The Genre of the game.  Can be used for informative purposes as well as for statistical evidence as to what genre is more popular. Could guide future pricing and distributor deals. (Useless in our case since the pseudo-random generator distributes all data equally, thus eliminating any possible statistical value.)
Publisher | Can be important to strike deals with distributors depending on how well the games of a specific publisher/studio are selling. Could also be used for marketing purposes and to inform the clients.
Dev_studio |
Metacritic-Score | 
PEGI-rating/Playtime | Trivial information about the game. Can be used for marketing, to inform the client or deduce pricing and discounts for a game.
Edition | Creates different pricing margins for the same games and is also used for dictating discounts.
Retail_price | Extremely important data for book-keeping 
Wholesale_price | Price of the game on wholesale
Max_Profit_margin | Maximum amount of the profit margin for the games
Possible_discount |  Based on how well a game is selling the maximum possible discount is decided. If a game does extremely well the possible discount drops and if it does poorly the discounts rise to boost sales.
Monthly_sales | 

### 4. Publishers ###

Field | Description
------|------------
Publisher_name | The name of the publisher, associated with publisher in the games table.
Publisher_cut | A cut that the publisher takes from every purchase when the store buys its stock. Based on publisher_demand. Not used in this application since all the stocking is calculated in the util_cost of the branch.
Publisher_sales | Statistics for the publisher world-wide used to calculate publisher demand.
Publisher_stock | The number of items the publisher is willing to sell for the year. Could be used to calculate cases of shortage and change the prices accordingly.
Publisher_demand | The general demand for a publisher.

### 5. Employees ###

Field | Description
------|------------
Empl_id | The unique id for every employee in the franchise.
Empl_name | The name of the employee.
Branch_id | The branch in which the employee belongs.
Status | Weather an employee is active or on leave. It is a paid leave so it still counts as a branch expense.
Base_sal | The standard monthly salary for every employee.
Commission | The percentage of a sale allocated towards the employee.

### 6. Online Orders ###

Field | Description
------|------------
Ord_id | The unique id of an order.
Ord_date | The date the order was placed.
Cust_id | The id of the customer that placed the order.
Prod_id | The id of the product ordered.
Urgency | The selected urgency selected by the user. Is used to calculate extra fees.
Warehouse_id | The unique id of the warehouse that will service the order.

### 7. Local_sales ###

Field | Description
------|-------------
Sale_id | The unique id of any local sale.
Cust_id | The id of the customer that made the purchase.
Sale_date | The date the sale took place.
Prod_id | The id of the product bought.
Branch_id | The branch the sale took place in.
Empl_id | The employee that closed the sale.

### 8. Branches ###

Field | Description
------|------------
Branch_id | The unique id of a branch.
Region | The regional coverage of a branch.
Manager_id | The id of the manager of the branch.
Manager_salary | The salary of the Manager of the branch.
Sales | The number of sales of non-game products in a store. These are accounted for as an average revenue value.
Util_cost | The monthly utility costs of the branch.

### 9. Warehouses ###

Field | Description
------|-----------
Warehouse_id | The unique id of the warehouse.
Region | The region that the warehouse is located in.
Emp_num | The number of employees occupied in the warehouse.
Shipping | Shows if the warehouse ships locally or globally.

# Suggestions for further development.

The needs of a franchise set of business trackers are vast. This application barely scratches the tip of the iceberg when it comes to covering all of them. Here are some suggestions for improving upon this application in the future.

•	Many more sales need to be recorded. An average of 30.000 sales per year for 100 employees should be expected by a healthy business chain.

•	Different tables are needed for recording weekly, monthly, and yearly data.

•	More tables needed to expand upon the publisher relations and operations of warehouses.

•	More queries that encompass both online and local environments could be created.

•	More elegant handling of the complex relationships dictating the pricing of the items, the salaries, and bookkeeping data needed.

•	The application should consider all customers, registered or not.

•	Need to expand upon non-game products, opening an entire subtree of interconnected tables for things like providers etc.

•	Separation between applications aimed at employees, managers, and global supervisors should be created, providing them with only the data needed to fit their needs.

