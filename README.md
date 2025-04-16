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



