# SQL server

## Delete

The delete statement has a little different syntax when it contains an alias

```
DELETE f FROM dbo.foods AS f WHERE f.name IN (...);
```
