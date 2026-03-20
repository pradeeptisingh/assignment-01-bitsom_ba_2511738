## Anomaly Analysis

### Insert Anomaly
The dataset includes product details which contain product_id and product_name and category and unit_price together with order information. The system requires an existing order before it allows the addition of a new product. 
For eg: The system requires users to provide order_id and customer_id and sales_rep_id before they can add the product "Laptop" which has not been sold yet.

### Update Anomaly
Customer information such as customer_name, customer_email, and customer_city is repeated across multiple rows for each order. 
For eg: The same customer_id appears multiple times because identical customer details are shown for each instance. If a customer changes their email or city, all rows must be updated. The data becomes inconsistent when any single row is missing.
In the same way, sale_rep_name and sale_rep_email are duplicated because they are heap within a row.

### Delete Anomaly
The system will remove all product data from its database if the last associated customer order for that product is deleted. 
For eg: The system will delete all product details including product_name and category and unit_price from its database if the last existing customer order for a product gets deleted from the system.


## Normalization Justification
The dataset demonstrates that unified table storage does not provide an easier solution for data management. The orders_flat dataset shows redundancy and data anomalies because it stores customer and product and sales representative information in a single table. The system stores customer information through three fields which include customer_name and customer_email and customer_city. A customer who places multiple orders will have their personal information duplicated throughout the system. The system requires updates for all rows when a customer changes their email address or moves to a new city. The system requires all rows to be present in order to maintain accurate data. The system stores product information through multiple rows which include product_name and category and unit_price details. The system requires all rows to receive updates whenever there is a price change which increases the chances of making mistakes. The dataset contains insert and delete anomalies which lead to data integrity problems. The system needs an order to exist before it can add a new product. The system deletes all product information when the user deletes the last order of that product.

The process of normalizing data into separate tables which include customers and products and orders and sales_reps and order_items tables leads to reduced redundancy and enhanced data integrity. The system establishes relationships between tables through foreign keys while each table keeps only its necessary attributes. The database needs normalization because it protects against data issues and supports system growth and ongoing development.
