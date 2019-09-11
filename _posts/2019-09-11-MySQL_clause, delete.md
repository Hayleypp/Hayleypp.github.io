TIL_MySQL



1. The order in which the MySQL get executed is

```mysql

# WHERE clause - SELECT clause - GROUP BY clause - HAVING clause - ORDER cluase
SELECT u.user_id, sum(p.price) as pay
FROM user_data as u LEFT JOIN product_data as p ON u.product = p.product_id
GROUP BY u.user_id
HAVING pay >= 550000000
ORDER BY sum(p.price) DESC;

```



2. TRUNCATE VS DELETE 

   To delete specific data in a row, for instance, "DELETE FROM sandbox WHERE id = 10;"

   To get rid of all, "TRUNCATE"

```mysql
# delete all data 
INSERT INTO sandbox
(name, value)
VALUES
('ghi', 30),('jkl',40),('mno',50);

TRUNCATE sandbox
```

