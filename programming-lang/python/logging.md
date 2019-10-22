## Usage
### Create logging
```
import logging
import logging.handlers as handlers

logger = logging.getLogger(__name__)
logger.setLevel(logging.INFO)

# Format, attributes reference https://docs.python.org/3/library/logging.html#logrecord-attributes
logger_formatter = logging.Formatter(
    '%(asctime)s %(name)s [%(levelname)s] %(message)s'
)
# handler, reference https://docs.python.org/3/library/logging.handlers.html#module-logging.handlers
logger_handler = handlers.RotatingFileHandler(
    'monitor.log',
    maxBytes=1024*1024,
    backupCount=5
)
logger_handler.setFormatter(logger_formatter)
logger.addHandler(logger_handler)
```
