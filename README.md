# KSA-Entertainment-Mysql
## Notice that some coloumns has "T" in it it actually represents thousand so we use CAST to change it
```sql
SELECT name, rating, 
       IF(review_count LIKE '%T', 
          CAST(REPLACE(review_count, 'T', '') AS UNSIGNED) * 1000, 
          CAST(review_count AS UNSIGNED)) AS actual_review_count
FROM cinemas 
ORDER BY actual_review_count DESC;
```
