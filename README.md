# Databases-Assignment_10
## Exercise 1
* **How many parks are located in exposed areas?**
```sql
SELECT 
    COUNT(*)
FROM 
    udsatte_byomraader, parkregister
WHERE 
    ST_Contains(udsatte_byomraader.wkb_geometry, parkregister.wkb_geometry);
```
Result: ```44```
* **How many trees are located in exposed areas?**
```sql
SELECT 
    COUNT(*)
FROM 
    gadetraer, udsatte_byomraader
WHERE 
    ST_Contains(udsatte_byomraader.wkb_geometry, gadetraer.wkb_geometry);
```
Result: ```4866```
