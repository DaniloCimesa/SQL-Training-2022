
 Write a complete SQL script with supporting comments applying all the concepts known so far that deletes some of tables not needed anymore.
```
--Deleted table Addresses of customer because I stored that data in table Customers.

drop table [Addresses of customers]

/*Deleted table Product_description because the data in this table is stored in table Products therefore 
I found table Product_description unnecessary. */

drop table Product_description

/*Deleted table Produc Model because all the data can be stored in Detailed description of product models*/

drop table Product_model
```
