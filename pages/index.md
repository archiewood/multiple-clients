# Orders for <Value data={orders} column=state/>

```sql orders
select * from needful_things.orders
```

```sql orders_by_week
select 
  date_trunc('week', order_datetime) as week,
  count(*) as orders
from needful_things.orders
group by all
order by 1
```

<LineChart
  data={orders_by_week}
  x=week
  y=orders
  title="Orders by week"
/>

```sql total_sales
select sum(sales) as total_sales from needful_things.orders
```

<BigValue
  data={total_sales}
  value=total_sales
  fmt=usd
/>







