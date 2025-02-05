# KSA-Entertainment-My sql
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
1. Select All Data
```sql
SELECT * FROM cinemas;
```

2. Get Cinemas with a Rating of 5
```sql


SELECT * FROM cinemas WHERE rating = 5;
```

3. Count the Number of Cinemas in Each City
```sql


SELECT location, COUNT(*) AS total_cinemas 
FROM cinemas 
GROUP BY location;
```
4. Find Cinemas with More than 10,000 Reviews
```sql


SELECT * FROM cinemas WHERE number_reviews > 10000;
```
5. Update a Cinema's Rating
```sql


UPDATE cinemas 
SET rating = 3 
WHERE name = 'Grand Cinemas Beirut';
```
6. Get the Top 5 Cinemas Based on Reviews
```sql


SELECT * FROM cinemas 
ORDER BY number_reviews DESC 
LIMIT 5;
```
7. Find Cinemas Containing "Mall" in Their Name
```sql


SELECT * FROM cinemas 
WHERE name LIKE '%Mall%';
```
8. Calculate the Average Number of Reviews Per Cinema
```sql


SELECT AVG(number_reviews) AS avg_reviews 
FROM cinemas;
```
9. Find Cinemas Located in Saudi Arabia
```sql


SELECT * FROM cinemas 
WHERE location LIKE '%Saudi Arabia%';
```
10. Delete a Cinema Entry
```sql


DELETE FROM cinemas 
WHERE name = 'Cinemacity Beirut';
```
11. Get the Cinema with the Highest Number of Reviews
```sql


SELECT * FROM cinemas 
ORDER BY number_reviews DESC 
LIMIT 1;
```
12. Find Cinemas with "Theater" in Their Name
```sql


SELECT * FROM cinemas 
WHERE name LIKE '%Theater%';
```
13. Show the Number of Cinemas with Each Rating
```sql


SELECT rating, COUNT(*) AS total_cinemas 
FROM cinemas 
GROUP BY rating 
ORDER BY rating DESC;
```

