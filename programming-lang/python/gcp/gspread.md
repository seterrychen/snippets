# Using gspread to control Google Sheet

```
pip install gspread oauth2client
```

gspread source code: https://github.com/burnash/gspread

Note: oauth2client is used for Authentication

## Google Sheet Usage Limits

This version of the Google Sheets API has a limit of 500 requests per 100 seconds per project, and 100 requests per 100 seconds per user. Limits for reads and writes are tracked separately. There is no daily usage limit.

## Authentication

```
import gspread
from oauth2client.service_account import ServiceAccountCredentials

scope = ['https://spreadsheets.google.com/feeds',      # should enable Google Sheet API
         'https://www.googleapis.com/auth/drive']      # should enable Google Drive API

credentials = ServiceAccountCredentials.from_json_keyfile_name(service_account.json, scope)

gc = gspread.authorize(credentials)
```

## Open a spreadsheet

Make sure that the worksheet exists and shared with service account. The worksheet key can get from url, such as https://docs.google.com/spreadsheets/d/1ymFkiHz5a2LRuRRhFYTdFlvqu0NH4T9PIHryioTwmhU/edit#gid=0, and key is 1ymFkiHz5a2LRuRRhFYTdFlvqu0NH4T9PIHryioTwmhU.

```
sh = gc.open_by_key("1ymFkiHz5a2LRuRRhFYTdFlvqu0NH4T9PIHryioTwmhU")
```

## Open a workshhet

```
wks = sh.get_worksheet(0)
wks = sh.sheet1
wks = sh.worksheet("ABC")
```

## fill value into a cell/cells

```
# a cell
wks.update_acell('B1', 'ABC')

# update celss
cells = wks.range('A1:C7')
for cell in cells:
    cell.value = 'abc'
wks.update_cells(cells)
```

## get value of a cell

```
value = wks.acell('B1').value
```
