## Installation
```
pip install pymongo
```

## Usage
### Connection
```
from pymongo import MongoClient

db = MongoClient(MONGODB_HOST)
```

### Query
```
db.collection_name.find({'name': 'xxx'})
```
