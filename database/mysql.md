## Usage
### How to convert timestamp to datetime in MySQL?
```
select from_unixtime(1300464000, "%Y-%m-%d %h %i %s") from table;
```

### Change the DEFINER of VIEW
```
SELECT CONCAT("ALTER DEFINER=`youruser`@`host` VIEW ", 
table_name, " AS ", view_definition, ";") 
FROM information_schema.views 
WHERE table_schema='your-database-name';
```

### How to get a list of MySQL views?
```
SHOW FULL TABLES IN database_name WHERE TABLE_TYPE LIKE 'VIEW';
```

### Find the definer of a view in MySQL
```
SHOW CREATE VIEW viewname
```
