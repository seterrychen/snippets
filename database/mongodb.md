## Installation
```
docker run --name some-mongo -d mongo:tag
```

## Usage
### inner join
```
db.collection_name.aggregate(
  [
    { $lookup: 
      {
        from: 'production',
        localField: 'name', 
        foreignField: 'foreign_name', 
        as: 'foreigns'
      },
      { $match: { foreigns: { $eq: [] }}}
    }
  ]
)
```

### Analyze Query Performance
#### Get executionStats for aggregate query
```
db.collection_name.explain('executionStats').aggregate(xxxxx)
```

## Client Tools
* [adminMongo](https://github.com/mrvautin/adminMongo) 
* [mongo-express](https://github.com/mongo-express/mongo-express)
