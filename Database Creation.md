
 Writing a complete SQL script with supporting comments applying all the concepts known so far that generate following tables that stores data about:

   - Addresses

   - Customers

   - Addresses of customers

   - Products

   - Products categories

   - Products description

   - Products models

   - Detailed products description of product models

   - Sales Orders (Headers)

   - Sales Orders (Details)

```
Create table [Product Categories]
(Product_category_id int,
 product_category_name varchar(25))


Create table [Addresses of customers]
(Customer_id int identity(1,1),
 Customer_Address varchar(40),
 Customer_Street_Num varchar(6))

 Create table Addresses
 (Store_id int identity (1,1) not null,
  Store_name varchar(10),
  Store_address varchar(40),
  Store_street_num varchar(6),
  Store_contact_person varchar(12),
  Store_contact varchar(20) not null)

  Create table Customers
  (ID int identity (1,1) not null,
   FirstName varchar(15) not null,
   LastName varchar (25) not null,
   Email varchar(50) not null,
   Password_ varchar(100) not null,
   Customer_phone varchar(20) not null,
   Customer_address varchar(40),
   Customer_street_num varchar(6))

   Create table Product_description
   (Product_id int not null,
    Product_cat_id int not null,
	product_name varchar(20) not null,
	product_description varchar(128))

	Create table Product_model
	(Product_Id int not null,
	 Product_name varchar(20) not null,
	 product_description varchar(128),
	 manufacturer varchar(50))

	 Create table Products
	 (Product_id int identity(1,1) not null,
	  Product_name varchar(30),
	  Product_description varchar(100),
	  product_category int)

	 Create table [Detailed description of product models]
	 (Model_ID tinyint identity (1,1) not null,
	  Product_ID int not null,
	  Product_Category_id int not null,
	  Product_model_name varchar(35),
	  Product_model_description varchar(50),
	  Packaging varchar(20),
	  Manufacturer varchar(30),
	  Gross_price smallint)

  
  Create table [Sales Orders(Header)]
(Order_ID smallint,
 Order_time datetime,
 Customer_ID int)


 Create table [Sales Orders(Details)]
 (Order_ID smallint,
 Order_summary varchar(100),
 order_from_store_id int )
 ```
