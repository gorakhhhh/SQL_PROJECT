# SQL_PROJECT
PROJECT: RESTAURANT MENU ANALYSIS IN SQL.
🔹 Level: Beginner
🔹 Database: restaurant_db

📖 Project Overview:
This project is designed to demonstrate SQL skills and techniques commonly used to analysis. Using the menu_items table, we will analyze menu sales data, identify trends, and answer key business questions. 

The project involves:
1.Setting up the database (restaurant_db)
2.Performing Exploratory Data Analysis (EDA)
3.Answering business-related queries using SQL

📌 Objectives for Menu Sales Analysis Project
1️⃣ Set up a Menu Sales Database
Create and populate a database with menu item data.
Ensure proper table structure and data integrity.

2️⃣ Data Cleaning
Identify and remove any records with missing or null values.
Standardize category names and correct inconsistencies in item names.

3️⃣ Exploratory Data Analysis (EDA)
Perform basic analysis to understand pricing distribution and category-wise trends.
Identify the highest and lowest-priced items.

4️⃣ Business Analysis
Use SQL queries to answer key business questions, such as best-selling categories, price trends, and most expensive items.
Provide insights to optimize menu pricing and category performance.


1.CREATING DATABASE:-
DROP SCHEMA IF EXISTS restaurant_db;
CREATE SCHEMA restaurant_db;
USE restaurant_db;

2.CREATE TABLE:-
CREATE TABLE menu_items (
  menu_item_id SMALLINT NOT NULL,
  item_name VARCHAR(45),
  category VARCHAR(45),
  price DECIMAL(5,2),
  PRIMARY KEY (menu_item_id)
);

3.FULL VALUES TO TABLE:-
INSERT INTO menu_items (menu_item_id, item_name, category, price) VALUES
(1, 'Margherita Pizza', 'Main Course', 8.99),
(2, 'Caesar Salad', 'Appetizer', 5.49),
(3, 'Chocolate Brownie', 'Dessert', 4.99),
(4, 'Lemon Iced Tea', 'Beverage', 3.29),
(5, 'Grilled Chicken Burger', 'Main Course', 9.49),
(6, 'Garlic Bread', 'Appetizer', 4.99),
(7, 'Vanilla Ice Cream', 'Dessert', 3.99),
(8, 'Mango Smoothie', 'Beverage', 4.59),
(9, 'Spaghetti Carbonara', 'Main Course', 10.99),
(10, 'French Fries', 'Appetizer', 3.99),
(11, 'Tiramisu', 'Dessert', 5.99),
(12, 'Espresso', 'Beverage', 2.99),
(13, 'BBQ Chicken Wings', 'Appetizer', 7.99),
(14, 'Veggie Wrap', 'Main Course', 6.99),
(15, 'Pineapple Juice', 'Beverage', 3.99),
(16, 'Cheese Nachos', 'Appetizer', 6.49),
(17, 'Chocolate Cake', 'Dessert', 5.49),
(18, 'Strawberry Milkshake', 'Beverage', 4.29),
(19, 'Pepperoni Pizza', 'Main Course', 9.99),
(20, 'Spring Rolls', 'Appetizer', 5.99),
(21, 'Tomato Basil Soup', 'Appetizer', 4.49),
(22, 'Chicken Alfredo Pasta', 'Main Course', 12.99),
(23, 'Mojito', 'Beverage', 5.29),
(24, 'Mango Sticky Rice', 'Dessert', 6.99),
(25, 'Onion Rings', 'Appetizer', 4.79),
(26, 'Fish Tacos', 'Main Course', 10.49),
(27, 'Green Tea', 'Beverage', 2.79),
(28, 'Raspberry Cheesecake', 'Dessert', 5.99),
(29, 'Club Sandwich', 'Main Course', 7.99),
(30, 'Hummus & Pita', 'Appetizer', 6.29),
(31, 'Cold Coffee', 'Beverage', 3.99),
(32, 'Red Velvet Cake', 'Dessert', 6.29),
(33, 'Butter Chicken', 'Main Course', 11.49),
(34, 'Stuffed Mushrooms', 'Appetizer', 5.79),
(35, 'Lassi', 'Beverage', 3.49),
(36, 'Gulab Jamun', 'Dessert', 4.49),
(37, 'Paneer Tikka', 'Appetizer', 7.49),
(38, 'Sushi Roll', 'Main Course', 14.99),
(39, 'Matcha Latte', 'Beverage', 4.59),
(40, 'Banana Split', 'Dessert', 5.99),
(41, 'Greek Salad', 'Appetizer', 6.49),
(42, 'Lamb Shawarma', 'Main Course', 13.99),
(43, 'Hot Chocolate', 'Beverage', 3.79),
(44, 'Pecan Pie', 'Dessert', 5.79),
(45, 'Mozzarella Sticks', 'Appetizer', 6.79),
(46, 'Vegetable Biryani', 'Main Course', 10.29),
(47, 'Watermelon Juice', 'Beverage', 3.49),
(48, 'Black Forest Cake', 'Dessert', 5.99),
(49, 'Bruschetta', 'Appetizer', 5.99),
(50, 'Tandoori Chicken', 'Main Course', 12.79),
(51, 'Americano', 'Beverage', 2.99),
(52, 'Apple Pie', 'Dessert', 5.49),
(53, 'Buffalo Cauliflower', 'Appetizer', 6.49),
(54, 'Beef Steak', 'Main Course', 15.99),
(55, 'Pomegranate Juice', 'Beverage', 4.29),
(56, 'Pumpkin Pie', 'Dessert', 5.79),
(57, 'Chicken Satay', 'Appetizer', 6.99),
(58, 'Pesto Pasta', 'Main Course', 11.29),
(59, 'Coconut Water', 'Beverage', 3.19),
(60, 'Creme Brulee', 'Dessert', 6.49),
(61, 'Stuffed Bell Peppers', 'Appetizer', 7.19),
(62, 'Ribeye Steak', 'Main Course', 17.49),
(63, 'Berry Smoothie', 'Beverage', 4.79),
(64, 'Tapioca Pudding', 'Dessert', 4.99),
(65, 'Deviled Eggs', 'Appetizer', 5.39),
(66, 'Grilled Salmon', 'Main Course', 16.99),
(67, 'Cappuccino', 'Beverage', 3.99),
(68, 'Blueberry Muffin', 'Dessert', 3.79),
(69, 'Bacon Wrapped Dates', 'Appetizer', 6.99),
(70, 'Mushroom Risotto', 'Main Course', 12.59),
(71, 'Iced Coffee', 'Beverage', 3.49),
(72, 'Lemon Tart', 'Dessert', 5.29),
(73, 'Chili Cheese Fries', 'Appetizer', 6.99),
(74, 'Shrimp Scampi', 'Main Course', 14.49),
(75, 'Chai Latte', 'Beverage', 4.19),
(76, 'Chocolate Mousse', 'Dessert', 5.89),
(77, 'Caprese Salad', 'Appetizer', 6.79),
(78, 'Pulled Pork Sandwich', 'Main Course', 9.99),
(79, 'Fresh Lime Soda', 'Beverage', 2.99),
(80, 'Macarons', 'Dessert', 4.99),
(81, 'Baked Brie', 'Appetizer', 7.49),
(82, 'Lasagna', 'Main Course', 13.49),
(83, 'Turmeric Latte', 'Beverage', 3.89),
(84, 'Churros', 'Dessert', 5.19),
(85, 'Prawn Cocktail', 'Appetizer', 8.99),
(86, 'BBQ Ribs', 'Main Course', 16.29),
(87, 'Cucumber Cooler', 'Beverage', 3.69),
(88, 'Peach Cobbler', 'Dessert', 5.79),
(89, 'Smoked Salmon Toast', 'Appetizer', 7.99),
(90, 'Lamb Chops', 'Main Course', 18.99),
(91, 'Hibiscus Tea', 'Beverage', 3.99),
(92, 'Baklava', 'Dessert', 6.49),
(93, 'Fried Pickles', 'Appetizer', 5.49),
(94, 'Duck Confit', 'Main Course', 19.49),
(95, 'Ginger Lemon Tea', 'Beverage', 3.59),
(96, 'Carrot Cake', 'Dessert', 5.99),
(97, 'Avocado Toast', 'Appetizer', 6.99),
(98, 'Seafood Paella', 'Main Course', 15.99),
(99, 'Espresso Martini', 'Beverage', 7.99),
(100, 'Tapioca Pudding', 'Dessert', 4.89);

4.CRUR OPERATION:-
CRUD Operations in SQL
CRUD stands for Create, Read, Update, and Delete—the four fundamental operations used to interact with a database.

1️⃣ CREATE (INSERT) - Add New Records
The CREATE operation is used to insert new records into a table using the INSERT statement.

Example: Add a new menu item to the menu_items table

INSERT INTO menu_items (menu_item_id, item_name, category, price)  
VALUES (101, 'Margherita Pizza', 'Main Course', 12.99);
✅ Effect: A new row is added to the menu_items table.

2️⃣ READ (SELECT) - Retrieve Records
The READ operation is used to fetch data from a table using the SELECT statement.

Example: Retrieve all menu items

SELECT * FROM menu_items;
✅ Effect: Displays all records from the menu_items table.

3️⃣ UPDATE (MODIFY) - Modify Existing Records
The UPDATE operation is used to modify existing data in a table using the UPDATE statement.

Example: Update the price of a menu item

UPDATE menu_items  
SET price = 14.99  
WHERE item_name = 'Margherita Pizza';
✅ Effect: The price of "Margherita Pizza" is updated to ₹14.99.

4️⃣ DELETE (REMOVE) - Remove Records
The DELETE operation is used to remove data from a table using the DELETE statement.

Example: Delete a menu item from the table
DELETE FROM menu_items  
WHERE item_name = 'Margherita Pizza';
✅ Effect: The row containing "Margherita Pizza" is removed from the menu_items table.

5.QUESTION AND ANSWERS :-

#1.view the menu_items table.

select * from menu_items;

#2.what are the most least and most explansive items in the menu.

select * from menu_items 
order by price;

select * from menu_items 
order by price desc;

#3.how many main cource are there in menu:

select * from menu_items where category='main course';

#4 give me expansive main course?

select * from menu_items where category='main course'
order by price desc;

#5.how many items in each category?

select category,count(item_name)
from menu_items
group by category;

#6.what are the avg dish price within the each category?

select category,avg(price)
from menu_items
group by category;

#7Find all menu items priced above ₹10.00.

SELECT * FROM menu_items WHERE price > 10.00;

#8. Display only item_name and price of all items.

SELECT item_name, price FROM menu_items;

#9. Count the total number of menu items.

SELECT COUNT(*) AS total_items FROM menu_items;

#10.Get the average price of all menu items.

select avg(price) as avg_price from menu_items;

#11.Find the total number of items in the "Dessert" category.

select count(*) as total_dessart from menu_items where category='dessert';

#12.List all menu items in ascending order of price.

select * from menu_items order by price;

#13.Get the second most expensive item from the menu.

select * from menu_items order by price desc
limit 1
offset 1;

#14. Find all menu items with "Pizza" in their name.

SELECT * FROM menu_items WHERE item_name LIKE '%Pizza%';

#15.Find all items priced between ₹5 and ₹10.

select * from menu_items where price between 5 and 10;

#16.Increase the price of all items by 10%.

UPDATE menu_items SET price = price * 1.10;
set sql_safe_updates =0

#17.Delete all items from the "Beverage" category.

delete FROM menu_items WHERE category = 'main course';
set sql_safe_updates =1


#18.Add a new item to the menu.

INSERT INTO menu_items (menu_item_id, item_name, category, price) 
VALUES (501, 'Schezwan Noodles', 'Main Course', 12.49);
