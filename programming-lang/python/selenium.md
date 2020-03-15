## Installation
```
pip install selenium
```

## Usage
### Remote connection(Firefox)
```
from selenium import webdriver
from selenium.webdriver.common.desired_capabilities import DesiredCapabilities

driver = webdriver.Remote(
    command_executor=f'http://{ip}:4444/wd/hub',
    desired_capabilities=DesiredCapabilities.FIREFOX
)
```

### scroll to bottom
```
driver.execute_script("window.scrollTo(0, document.body.scrollHeight);")
```
