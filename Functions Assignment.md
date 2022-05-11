Write a complete SQL script with supporting comments applying all the concepts known so far that generates user defined function showing product price, 
both net and gross value. 
For example, if an item costs 80 in net, the udf will have to add 20% to that price in order to show gross value. 
Also, if we have an item having gross price of 100, we need to create udf that will show net value of that item.

--Creating function which returns net price values for input gross prices.

```
alter function fnAssignment12
(@GrossPrice int)

returns int
as
begin
return @GrossPrice * 0.8
end
go

select 
Product_model_name
, product_model_description
, gross_price
, dbo.fnAssignment12 (Gross_Price) as NetPrice
from [Detailed description of product models]
```


/*Created a function which returns a table containing model name, model description,
gross price and net price for user specified name of the model. 
Also added a little extra into the calculation of net value, 
if a product model is Alcohol or Cigarettes the taxes are 30% instead of usual 20.
*/

```
Create function fnAssignment12a
(@ProductName varchar(50))
returns table
as return
Select 
  Product_model_name as Product
, product_model_description as [Product description]
, gross_price [Gross price of the product]
, case when Product_Category_id in(Select Product_Category_id from [Product Categories] where product_category_name='Cigarete' or product_category_name='Alkohol') then Gross_price*0.7
 else Gross_price*0.8 end as [Net price of the product]
 from [Detailed description of product models]
where Product_model_name like '%'+@ProductName+'%'

select * from dbo.fnAssignment12a ('Carsl')

```
