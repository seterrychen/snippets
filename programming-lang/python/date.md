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
```

## To get last day of the month

```
import calendar
calendar.monthrange(2002, 1)   # return tuple(1, 31)  1 is Tuesday
calendar.monthrange(2008, 2)   # return tuple(4, 29)  4 is Friday
```

Note: weekday of python, Monday is 0 and Sunday is 6

## dateTime to string, str to datetime

```
datetime.today().strftime('%m')                # if today is 2019/03/04, it will print '02'
datetime.strptime('2019/03/04', '%Y/%m/%d')    # str to datetime
```
