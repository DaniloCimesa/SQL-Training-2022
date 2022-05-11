Create stored procedure that will generate ordering report that takes parameters used to bound that report to start and end date needed to be shown, 
for example sp_sles_report(from_date, to_date).


/*Procedure which returns all orders between start and end date which user specified.*/

```
alter procedure sp_sles_report
(@startdate varchar(25),
@Enddate varchar(25))

 as
 begin
Select Sh.Order_ID, Order_time, FirstName+' '+LastName as Name, Order_summary as 'Order', Store_name as Store
from [Sales Orders(Header)] sh
join [Sales Orders(Details)] sd
on sh.Order_ID=sd.Order_ID
join Customers C
on sh.Customer_ID=c.ID
join Addresses A
on sd.order_from_store_id=a.Store_id
where Order_time between @startdate and @Enddate
end

exec dbo.sp_sles_report '2022-3-25', '2022-4-01'

```
