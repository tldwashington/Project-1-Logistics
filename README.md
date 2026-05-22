## Project-1-Logistics

Scenario:

You’re working with the logistics analytics team at a national shipping company. Your job is to analyze delivery records, identify trends in carrier performance, and ensure accurate customer contact data for future notifications. You’ll work with three related tables: Shipment, Carrier, and Customer.

  1. Calculate the average deliver time per carrier, ordered from slowest to fastest. 

  2. Generate a list of distinct delivery statuses used across all shipments.

  3. Create a list of customers showing their full names and label missing emails as 'email needed'.

  4. List all shipments with customer and carrier names, including shipments for customers who don't have an email address on file.

## Skills Practiced

- SELECT statements
- DISTINCT queries
- Aggregate functions (AVG)
- GROUP BY
- ORDER BY
- Table aliases
- INNER JOIN operations
- SQL debugging and query refinement

## Repository Structure

- `schema.sql` → database table creation
- `sample_data.sql` → mock logistics dataset
- `queries.sql` → completed SQL analysis queries
- `notes.md` → debugging notes and learning reflections
- `screenshots/` → query outputs and workflow error messages

## Learning Context

This project was completed as part of a SQL learning series through Data Analytics Simplified in 2026. The exercises focused on building foundational SQL querying skills while documenting analytical thinking and debugging workflows.

## Key Takeaways

- Learned how aggregate functions interact with GROUP BY
- Improved understanding of table aliases and JOIN logic
- Practiced debugging SQL syntax and query structure errors
- Observed how AVG() handles NULL values in MySQL
