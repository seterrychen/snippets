## Install

```
pip install beautifulsoup4
```


## Usage
### Parser
```
from bs4 import BeautifulSoup

parser = BeautifulSoup(html_doc, 'html.parser')
```


### Search
To find '\<a\>'

```
parser.find_all('a')
```

To find elements which included href and its value is started with '/my_link' using regex pattern

```
links = soup.find_all(href=re.compile("^/my_link\d"))
```

