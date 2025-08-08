# Women Clothing E-commerce Sales Analysis  

## 📌 Project Overview  
This project analyzes an e-commerce dataset for women's clothing sales using **MySQL**.  
The dataset contains order details such as SKU, color, size, price, quantity, and revenue.  
The goal is to perform SQL-based analysis to extract meaningful business insights.

---

## 📂 Dataset Description  

**Table Name:** `women_clothing_ecommerce_sales`  

| Column Name  | Description |
|--------------|-------------|
| `order_id`   | Unique order ID |
| `order_date` | Date of the order |
| `sku`        | Stock Keeping Unit (product code) |
| `color`      | Color of the item |
| `size`       | Size of the item |
| `unit_price` | Price per unit |
| `quantity`   | Number of units sold |
| `revenue`    | Total revenue from the order |

---

## 🛠 SQL Tasks Performed  

### 1️⃣ Basic Queries  
```sql
-- View all data
SELECT * FROM women_clothing_ecommerce_sales;

-- Orders after a certain date
SELECT * FROM women_clothing_ecommerce_sales
WHERE order_date > '2022-01-01';
2️⃣ Aggregate Functions (SUM, AVG)
-- Total Revenue
SELECT SUM(revenue) AS total_revenue 
FROM women_clothing_ecommerce_sales;

-- Average Unit Price
SELECT AVG(unit_price) AS avg_price 
FROM women_clothing_ecommerce_sales;
3️⃣ Grouping
-- Revenue by color
SELECT color, SUM(revenue) AS total_revenue
FROM women_clothing_ecommerce_sales
GROUP BY color
ORDER BY total_revenue DESC;
4️⃣ Subqueries
-- Products with above-average price
SELECT * 
FROM women_clothing_ecommerce_sales
WHERE unit_price > (
    SELECT AVG(unit_price) 
    FROM women_clothing_ecommerce_sales
);
5️⃣ Views
-- Create a view for monthly revenue
CREATE VIEW monthly_sales AS
SELECT DATE_FORMAT(order_date, '%Y-%m') AS month, 
       SUM(revenue) AS total_revenue
FROM women_clothing_ecommerce_sales
GROUP BY month;
#Screenshots
<img width="1149" height="949" alt="Screenshot 2025-08-08 204047" src="https://github.com/user-attachments/assets/c282a00f-6e34-49a1-a878-ece61ffa1e7d" />
<img width="1633" height="1017" alt="Screenshot 2025-08-08 204104" src="https://github.com/user-attachments/assets/cb3f9776-cc28-4c9e-a406-2b2a4fc4f397" />
<img width="724" height="969" alt="Screenshot 2025-08-08 204128" src="https://github.com/user-attachments/assets/6c254a6e-68c6-431a-a385-14f70b2bca9a" />
<img width="825" height="724" alt="Screenshot 2025-08-08 204144" src="https://github.com/user-attachments/assets/3f6b5509-d286-43c4-a70f-1a735f61beb9" />
<img width="805" height="569" alt="Screenshot 2025-08-08 204211" src="https://github.com/user-attachments/assets/634935b7-3931-421f-9283-b5423d360e9d" />
<img width="778" height="498" alt="Screenshot 2025-08-08 204226" src="https://github.com/user-attachments/assets/8021e2fa-22db-419a-abb0-856ee792dc90" />

