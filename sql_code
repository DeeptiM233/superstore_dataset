CREATE DATABASE Superstore;
USE Superstore;
CREATE TABLE Superstore_data (
    OrderID VARCHAR(20),
    OrderDate DATE,
    ShipDate DATE,
    ShipMode VARCHAR(20),
    CustomerID VARCHAR(20),
    CustomerName VARCHAR(50),
    Segment VARCHAR(20),
    Country VARCHAR(50),
    City VARCHAR(50),
    State VARCHAR(50),
    PostalCode VARCHAR(10),
    Region VARCHAR(20),
    ProductID VARCHAR(20),
    Category VARCHAR(50),
    SubCategory VARCHAR(50),
    ProductName VARCHAR(100),
    Sales DECIMAL(10, 2),
    Quantity INT,
    Discount DECIMAL(3, 2),
    Profit DECIMAL(10, 4)
);
select* from Superstore_data;

SELECT ProductID, sales, profit
FROM  Superstore_data
WHERE quantity <= 1;
SELECT * FROM Superstore_data ORDER BY Category ASC;

SELECT Category, ShipMode, SubCategory
FROM Superstore_data
WHERE ShipMode IN (
    SELECT ShipMode
    FROM Superstore_data
    WHERE SubCategory = 'Art'
);
CREATE VIEW view_subcategory_analysis AS

SELECT 
    SubCategory,
    SUM(Quantity) AS TotalQuantity,
    AVG(Discount) AS AverageDiscount
FROM Superstore_data
GROUP BY SubCategory;
SELECT * FROM view_subcategory_analysis;

-- Single-Column Indexes
CREATE INDEX idx_subcategory ON Superstore_data (SubCategory);
CREATE INDEX idx_shipmode ON Superstore_data (ShipMode);

SHOW INDEX FROM Superstore_data;

