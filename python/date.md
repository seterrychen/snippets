# Date snippets

## Date format

```
import datetime

d = datetime.date.today()
d.strftime('%m')      # ex: 03
d.month
```

## Arithmetic operation on a date

ex: get last month

```
from datetime import date, timedelta

fisrt_day_of_this_month = date.today().replace(day=1)
last_day_of_last_month = first_day_of_this_month - timedelta(days=1)
print(d.strftime('%m'))   # if today is 2019/03/04, it will print '02'
```
