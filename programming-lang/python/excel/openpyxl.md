# Using openpyxl to read/write Excel

```
pip install openpyxl
```

## [Document](https://openpyxl.readthedocs.io/en/stable/)

## Create a empty workbook

```
from openpyxl import Workbook

wb = Workbook()
wb.save('xxxx.xlsx')
```

## Worksheet

```
ws = wb.active                             # Get the currently active sheet or None
ws = wb.get_sheet_by_name("title_name")    # Returns a worksheet by its name.
ws2 = wb.create_sheet("title_name")        # Create a new sheet naming "title_name"
```

## write a row

```
ws.append(['This is A1', 'This is B1', 'This is C1'])
``` 
