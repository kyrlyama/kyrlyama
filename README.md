CREATE TABLE Customers (
    cust_id VARCHAR(10) PRIMARY KEY,
    cust_name VARCHAR(255),
    contact_name VARCHAR(255),
    email VARCHAR(255)
);

CREATE TABLE Products (
    prod_id VARCHAR(10) PRIMARY KEY,
    prod_name VARCHAR(255),
    supplier_id VARCHAR(10),
    unit_price NUMBER(10, 2)
);

CREATE TABLE Orders (
    order_num INT PRIMARY KEY,
    order_date DATE,
    cust_id VARCHAR(10)
);

CREATE TABLE OrderItems (
    order_num INT,
    order_item INT,
    prod_id VARCHAR(10),
    quantity INT,
    item_price DECIMAL(10, 2)
);

-- Заполнение таблиц данными
-- Populate Customers table
INSERT INTO Customers(cust_id, cust_name, contact_name, email)
VALUES('1000000001', 'Customer 1', 'Contact 1', 'customer1@example.com');

INSERT INTO Customers(cust_id, cust_name, contact_name, email)
VALUES('1000000003', 'Customer 3', 'Contact 3', 'customer3@example.com');

INSERT INTO Customers(cust_id, cust_name, contact_name, email)
VALUES('1000000004', 'Customer 4', 'Contact 4', 'customer4@example.com');

INSERT INTO Customers(cust_id, cust_name, contact_name, email)
VALUES('1000000005', 'Customer 5', 'Contact 5', 'customer5@example.com');

-- Populate Products table
INSERT INTO Products(prod_id, prod_name, supplier_id, unit_price)
VALUES('BR01', 'Product 1', 'DLL01', 5.49);

INSERT INTO Products(prod_id, prod_name, supplier_id, unit_price)
VALUES('BR02', 'Product 2', 'DLL02', 8.99);

INSERT INTO Products(prod_id, prod_name, supplier_id, unit_price)
VALUES('BR03', 'Product 3', 'DLL01', 10.99);

INSERT INTO Products(prod_id, prod_name, supplier_id, unit_price)
VALUES('BNBG01', 'Product 4', 'DLL03', 2.99);

INSERT INTO Products(prod_id, prod_name, supplier_id, unit_price)
VALUES('BNBG02', 'Product 5', 'DLL03', 2.99);

INSERT INTO Products(prod_id, prod_name, supplier_id, unit_price)
VALUES('BNBG03', 'Product 6', 'DLL03', 2.99);

INSERT INTO Products(prod_id, prod_name, supplier_id, unit_price)
VALUES('RGAN01', 'Product 7', 'DLL04', 4.49);

-- Populate Orders table
INSERT INTO Orders(order_num, order_date, cust_id)
VALUES(20005, TO_DATE('2020-05-01', 'yyyy-mm-dd'), '1000000001');

INSERT INTO Orders(order_num, order_date, cust_id)
VALUES(20006, TO_DATE('2020-01-12', 'yyyy-mm-dd'), '1000000003');

INSERT INTO Orders(order_num, order_date, cust_id)
VALUES(20007, TO_DATE('2020-01-30', 'yyyy-mm-dd'), '1000000004');

INSERT INTO Orders(order_num, order_date, cust_id)
VALUES(20008, TO_DATE('2020-02-03', 'yyyy-mm-dd'), '1000000005');

INSERT INTO Orders(order_num, order_date, cust_id)
VALUES(20009, TO_DATE('2020-02-08', 'yyyy-mm-dd'), '1000000001');

-- Populate OrderItems table
INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20005, 1, 'BR01', 100, 5.49);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20005, 2, 'BR03', 100, 10.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20006, 1, 'BR01', 20, 5.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20006, 2, 'BR02', 10, 8.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20006, 3, 'BR03', 10, 11.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20007, 1, 'BR03', 50, 11.49);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20007, 2, 'BNBG01', 100, 2.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20007, 3, 'BNBG02', 100, 2.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20007, 4, 'BNBG03', 100, 2.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20007, 5, 'RGAN01', 50, 4.49);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20008, 1, 'RGAN01', 5, 4.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20008, 2, 'BR03', 5, 11.99);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20008, 3, 'BNBG01', 10, 3.49);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20008, 4, 'BNBG02', 10, 3.49);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20008, 5, 'BNBG03', 10, 3.49);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20009, 1, 'BNBG01', 250, 2.49);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20009, 2, 'BNBG02', 250, 2.49);

INSERT INTO OrderItems(order_num, order_item, prod_id, quantity, item_price)
VALUES(20009, 3, 'BNBG03', 250, 2.49);
