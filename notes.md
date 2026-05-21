-- Scenario:
-- You’re working with the logistics analytics team at a national shipping company. Your job is to analyze delivery records, identify trends in carrier performance, and ensure accurate customer contact data for future notifications. 
-- You’ll work with three related tables: Shipment, Carrier, and Customer.

-- 1. Calculate the average deliver time per carrier, ordered from slowest to fastest. 

-- 2. Distinct Delivery Statuses
-- Goal: Generate a list of distinct delivery statuses used across all shipments.

-- Analysis:
-- I know I am pulling sh.delivery_status, and need a DISTINCT query, but I don't remember where to start. I'll start with my gut:
  DISTINCT sh.delivery_status
  
-- That wasn't correct - too simple of a query. But maybe I need to SELECT the sh.delivery_status first, then query to pull only DISTINCT delivery statuses. Let's try:
  SELECT DISTINCT sh.delivery_status

-- I got this error message:
-- "unknown table 'sh' in field list", which means I need to create the alias first for SQL to recognize what table I'm referencing (Shipment). Let's try this:
  SELECT FROM Shipment sh

-- I got this error message:
-- "check the manual that corresponds to your MySQL server version for the right syntax to use near 'FROM Shipment sh -- Create a list of customers showing their full names and lab' at line 25." (in this document, line 19)

-- I can tell from the schema that my output should return a short list of two distinct delivery_status (Delivered and Pending). I know I need to:
-- 1. create an alias for table Shipment sh
-- 2. use SELECT and DISTINCT functions
-- 3. pull values from Shipment

-- Let's try:

SELECT DISTINCT FROM Shipment sh
  sh.delivery_status AS distinct_status
    
-- I got this error message: 
-- "check the manual that corresponds to your MySQL server version for the right syntax to use near 'FROM Shipment sh sh.delivery_status AS distinct_status -- Create a list of cus' at line 35" (in this document, line 31). 
-- I'm a bit stumped but I feel like all the pieces are there, and not in the right order or format. When the error says "-- Create a list of cus" it's reading non-query text from the schema code, at least in a way that prevents MY query from running. I've gotten too far off base - I don't need to rename that column!

-- Let me step back and build up: I know how to pull a list of all delivery status records (not types). I'd run:
  SELECT * FROM Shipment
-- (insert screenshot here)

-- Great, that gave me what I expected: the full Shipment table with all columns and values. I'm confident in running a query to output just the delivery_status column:
  SELECT delivery_status FROM Shipment
-- (insert screenshot here)

-- Yes, on the right track. I have one column, delivery_status, that returns ALL records. NOW I need to use the DISTINCT function to give me an output of just two rows to read "Delivered" and "Pending." But order and syntax matters. Let's try:
  SELECT DISTINCT delivery_status FROM Shipment
-- (insert screenshot here)

-- Result: I knew the output should've resulted in two statuses under delivery_status: Delivered and Pending. The DISTINCT function tells SQL to pull unique values - we did not need every record of every delivery status.
-- Key takeaways:
-- 1. I needed to break down and build up to the query being asked. I had all the right elements and correctly identified which table, column, and values were needed to query and execute.
-- 2. I wasted time and confused myself on creating an alias for the Shipment table, and didn't need to, especially since this is such a small data set. My first couple attempts took me away from the query.
-- 3. I knew DISTINCT function would be used, and placement matters. I got sidetracked, attempting to use our SELECT FROM WHERE query foundation, and using DISTINCT later.


3. Create a list of customers showing their full names and label missing emails as 'email needed'.

4. Generate a list of distinct delivery statues used across all shipments.  

5. List all shipments with customer and carrier names, including shipments for customers who don't have an email address on file. 
