CREATE TABLE sales_data AS
SELECT DISTINCT *
FROM sales_data;



UPDATE sales_data
SET price = 0
WHERE price IS NULL;


UPDATE sales_data
SET total_amount = quantity * price
WHERE total_amount IS NULL;


ALTER TABLE sales_data
ALTER COLUMN order_date TYPE DATE
USING TO_DATE(order_date, 'MM/DD/YYYY');

ALTER TABLE sales_data
RENAME COLUMN "Customer_Name" TO customer_name;
ALTER TABLE sales_data
RENAME COLUMN "Order_Date" TO order_date;
ALTER TABLE sales_data
RENAME COLUMN "Total_Amount" TO total_amount;

ALTER TABLE sales_data
ALTER COLUMN quantity TYPE INT USING quantity::INT;

ALTER TABLE sales_data
ALTER COLUMN price TYPE NUMERIC USING price::NUMERIC;

ALTER TABLE sales_data
ALTER COLUMN total_amount TYPE NUMERIC USING total_amount::NUMERIC;\

