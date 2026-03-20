## Anomaly Analysis

### Insert Anomaly
The database table contains three types of information which include product details and customer information and order records. The product addition process requires an existing customer order before a new product can be added. 
The system requires order_id and customer_id fields to create a new product even if the product has never been ordered. 
The system stops users from entering product information because it requires them to complete all associated data.

### Update Anomaly
The system stores all customer information which includes their name and city details in a single database table which results in multiple rows displaying identical information. 
The system needs to update all existing customer records when a customer changes their residence to a different city. The database will display inconsistent information when one row of data is not included.

### Delet Anomaly
The deletion of the final order which includes a specific product leads to the removal of product details from the database. The system loses product information because product details still exist. 
