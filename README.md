# DB-Assignment

## 1-Relationship between "Product" and "Product_Category" entities:
Based on the names of the entities, it appears that there is a relationship between the "Product" and "Product_Category" tables/entities. This relationship suggests that each product belongs to a specific category. It implies a one-to-many relationship where one product category can have multiple products, but each product can only belong to one category.

## 2-Ensuring valid category assignment:
To ensure that each product in the "Product" table has a valid category assigned to it, we can enforce referential integrity constraints. This can be achieved by setting up a foreign key relationship between the "Product" and "Product_Category" tables. The foreign key constraint ensures that the value in the "Product_Category" column of the "Product" table matches with a valid primary key value from the "Product_Category" table. If a product is inserted or updated with an invalid category, the database will reject the operation, thereby ensuring the validity of the category assignment.

## 3-Creating the schema in a Database script or ORM:
```sql
-- Create the Product_Category table
CREATE TABLE Product_Category (
  category_id INT PRIMARY KEY,
  category_name VARCHAR(255)
);

-- Create the Product table with a foreign key constraint
CREATE TABLE Product (
  product_id INT PRIMARY KEY,
  product_name VARCHAR(255),
  category_id INT,
  FOREIGN KEY (category_id) REFERENCES Product_Category(category_id)
);
```
