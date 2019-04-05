# Databases-Assignment_10
## Exercise 1
* How many parks are located in exposed areas?
```sql
SELECT 
    COUNT(*)
FROM 
	  udsatte_byomraader, parkregister
WHERE 
	  ST_Contains(udsatte_byomraader.wkb_geometry, parkregister.wkb_geometry);
```
* How many trees are located in exposed areas?
```sql

```
