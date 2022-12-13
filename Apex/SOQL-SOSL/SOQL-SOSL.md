# SOQL and SOSL Query
Boilerplate for SOQL and SOQL Query languages.

## SOQL Query

```
SELECT field1, 
       field2,
       field3 etc
FROM Account
//Some Optional search parameters
WHERE field1 = value
OR field2 = value
OR field3 = value
ORDER BY fieldName DESC | ASC 
LIMIT 10
GROUP BY fieldName
```

## SOSL Query

```
FIND {textString} IN ALL FIELDS 
                  RETURNING object1(field),
                            object2(field1, field2) //or more
```