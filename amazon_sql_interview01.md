#### Questions: 
In this question, I would like to have customer id within table **customer** but not in table **trans**.

```sql
-- solution 01

SELECT 
  c.customer_id
FROM customer c
WHERE c.customer_id NOT IN (
  SELECT 
    customer_id 
  FROM trans
)
;
```

<br/>       

```sql
-- solution 02
SELECT 
  c.customer_id
FROM customer c
LEFT JOIN trans t
ON c.customer_id = t.customer_id
WHERE t.customer_id IS NULL
;
```
