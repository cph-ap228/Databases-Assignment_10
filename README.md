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

---

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

## Exercise 2
* **How many bike racks are placed along routes for heavy traffic?**
Due to the fact that we're dealing with a MULTISTRING and a POINT, there's no way currently implemented to figure out if the POINT is placed "along a route" (i.e. if any of the POINTs that each MULTISTRING is made up of is X meters/centimeters from each other). We initially thought ST_Distance() would be able to accomplish this, but it throws an error.
