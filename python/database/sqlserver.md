# MS SQL Server

```
pip install pyodbc
```

## Driver

Download from [website](https://docs.microsoft.com/en-us/sql/connect/odbc/linux-mac/installing-the-microsoft-odbc-driver-for-sql-server?view=sql-server-2017)

### [Using an ODBC driver](https://github.com/mkleehammer/pyodbc/wiki/Connecting-to-SQL-Server-from-Windows)

* {SQL Server} - released with SQL Server 2000
* {SQL Native Client} - released with SQL Server 2005 (also known as version 9.0)
* {SQL Server Native Client 10.0} - released with SQL Server 2008
* {SQL Server Native Client 11.0} - released with SQL Server 2012
* {ODBC Driver 11 for SQL Server} - supports SQL Server 2005 through 2014
* {ODBC Driver 13 for SQL Server} - supports SQL Server 2005 through 2016
* {ODBC Driver 13.1 for SQL Server} - supports SQL Server 2008 through 2016
* {ODBC Driver 17 for SQL Server} - supports SQL Server 2008 through 2017


## Connect to server

```
import pyodbc

conn_str = "DRIVER={{driver_name}};Server={ip};port=1433;Network Library=DBMSSOCN;Database={db_name};uid={account};pwd={pwd};"
conn = pyodbc.connect(conn_str)
```

## Execute SQL statement

### Insert a record

```
cursor = conn.cursor()
cursor.execute("insert into products(id, name) values (?, ?)", 'pyodbc', 'awesome library')
cursor.commit()
```

### Batch insert

```
cursor = conn.cursor()
data = [
    ['pyodbc', 'awesome library'],
    ['123', '321']
]
cursor.executemany("insert into products(id, name) values (?, ?)", data)
cursor.commit()
```


## Q & A

### Reason: image not found

```
>>> import pyodbc
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ImportError: dlopen(/Library/Python/2.7/site-packages/pyodbc.so, 2): Library not loaded: /usr/local/lib/libodbc.2.dylib
  Referenced from: /Library/Python/2.7/site-packages/pyodbc.so
  Reason: image not found
```

Ans: 

```
brew install unixodbc  
```
