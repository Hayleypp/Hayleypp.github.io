# (Python) sys.stdin.readline



* Rather than input(), use "sys.stdin.radline()"

```python
import sys
recommend = map(int, sys.stdin.readline())
# recommend = [1,2,3,4,5,6,7]
```

```
import sys
n = input()
recommend = [sys.stdin.readline() for i in range(n)]
# recommend = ["1 2 3", "4 5 6", "7 8 9"]
```













# (MySQL) Stored Procedure



```sql
DELIMITER $$
CREATE PROCEDURE CountOrderByStatus(
 IN orderStatus VARCHAR(25),
 OUT total INT)
BEGIN
 SELECT count(orderNumber)
 INTO total
 FROM orders
 WHERE status = orderStatus;
END$$
DELIMITER;
```

 