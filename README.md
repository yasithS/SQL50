## SELECT

### 1757. Recyclable and Low Fat Products
```
select product_id from Products 
where low_fats = "Y" and recyclable = "Y"
```
### 584. Find Customer Referee
```
select name from Customer
where referee_id != 2 or referee_id is null
```

### 595. Big Countries
```
select name, population, area from World
where area >= 3000000 or population >= 25000000
```

### 1148. Article Views I
```
select distinct author_id as id
from views
where author_id = viewer_id 
order by id
```

### 1683. Invalid Tweets
```
select tweet_id from tweets
where length(content) > 15
```

## BASIC JOINS

### 1378. Replace Employee ID With The Unique Identifier
```
select en.unique_id , e.name 
from Employees as e left join EmployeeUNI as en
on e.id = en.id
```

### 1068. Product Sales Analysis I
```
select p.product_name, 
        s.year, 
        s.price 
from sales s
join product p on s.product_id = p.product_id
```

### 1581. Customer Who Visited but Did Not Make Any Transactions
```
select v.customer_id, count(*) as count_no_trans
from visits v 
left join transactions t on v.visit_id = t.visit_id 
where t.transaction_id is null 
group by v.customer_id; 
```

### 197. Rising Temperature
```
select w1.id 
from weather w1
join weather w2 on date(w1.recordDate) = date_add(w2.recordDate, interval 1 day)
where w1.temperature > w2.temperature
```

### 1661. Average Time of Process per Machine
```
WITH proceess_time_cte AS (
    SELECT a1.machine_id,
        (a2.timestamp - a1.timestamp) as processing_time
    FROM activity a1
    JOIN activity a2 ON 
        a1.machine_id = a2.machine_id AND 
        a1.process_id = a2.process_id AND
        a1.activity_type = 'start' AND
        a2.activity_type = 'end'
)
SELECT machine_id, 
        ROUND(AVG(processing_time),3) as processing_time
from proceess_time_cte
GROUP BY machine_id
```

### 577. Employee Bonus
```
SELECT name,
        bonus 
FROM employee e
LEFT jOIN bonus b ON e.empId = b.empId
WHERE b.bonus < 1000 or b.bonus IS NULL
```


