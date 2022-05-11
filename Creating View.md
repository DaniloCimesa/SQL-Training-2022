Write a complete SQL script with supporting comments applying all the concepts known so far that generates view showing sales orders including both Header and Details per order.

```
Create view  vwAssignment11 as

Select 
 sh.Order_ID
, Order_time
, Customer_address as Delivery_Address
, Order_summary
, FirstName+ ' '+ LastName as Name
, Customer_phone as contact
, Store_name as Ordered_from
from [Sales Orders(Header)] sh
join [Sales Orders(Details)] sd
on sh.Order_ID=sd.Order_ID
join Customers c
on sh.Customer_ID=c.ID
join Addresses a
on sd.order_from_store_id=a.Store_id
```
