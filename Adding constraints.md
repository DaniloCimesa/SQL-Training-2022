

Added not null constraint to Product category id column in table Product Categories. 
Added a primary key constraint to Product Categories table. 
```
Alter table [Product Categories]
alter column product_category_id int not null

alter table [Product Categories]
add constraint PK_Product_category_Id primary key (product_category_id)
```

Added primary key constraint to Addresses table. Added not null constraint to Addresses table column Store_name
```
alter table Addresses
add constraint PK_Store_id primary key (Store_id)

Alter table Addresses
alter column Store_name varchar(10) not null
```
Added primary key constraint to Customers table.
```
alter table Customers
add constraint PK_ID primary key (ID)
```
Added primary key constraint to Products table. Added foreign key constraint to Products table.
```
alter table Products
add constraint PK_Product_id primary key (Product_id)

alter table Products
add constraint fk_product_category foreign key (product_category) references [Product categories](Product_category_id)
```

Added primary key constraint to Detailed description of product models. 
Added foreign key constraints referencing from Products and Product categories.
```
alter table [Detailed description of product models]
add constraint PK_Model_ID primary key (Model_ID)

alter table [Detailed description of product models]
add constraint fk_product_id foreign key (product_id) references Products (Product_id)

alter table [Detailed description of product models]
add constraint fk_product_category_id foreign key (product_category_id) references [Product categories] (Product_category_id)

alter table [Detailed description of product models]
alter column product_model_name varchar(50)
```
Added primary key constraint to Sales Orders (Header), before that had to alter column Order_ID to be not nullable.
Added foreign key constraint where primary key is ID referenced from Customers table.
```
Alter table [Sales Orders(Header)]
alter column Order_ID smallint not null

alter table [Sales Orders(Header)]
add constraint PK_Order_ID primary key (Order_ID)

alter table [Sales orders(Header)]
add constraint fk_customer_id foreign key (customer_id) references Customers (ID)
```

Added foreign key constraint to Sales Orders(Details), where primary key is order_id from sales orders(headers).
Added another foreign key constraint to Sales Orders(Details), where primary key is store_id from Addresses.
```
alter table [Sales orders(Details)]
add constraint fk_order_id foreign key (order_id) references [Sales Orders(Header)] (Order_id)

alter table [Sales orders(Details)]
add constraint fk_order_from_store_id foreign key (order_from_store_id) references Addresses (Store_id)
```
