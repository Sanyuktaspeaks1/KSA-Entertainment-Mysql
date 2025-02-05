# KSA-Entertainment-Mysql
## Renaming Coloumn
```sql
RENAME TABLE cleaned_file TO cinemas;
```

## Notice that some coloumns has "T" in it it actually represents thousand so we use CAST to change it
```sql
UPDATE cinemas
SET number_reviews = 
    CASE 
        WHEN review_count LIKE '%T%' THEN CAST(REPLACE(review_count, 'T', '') AS UNSIGNED) * 1000
        ELSE review_count
    END;

```
