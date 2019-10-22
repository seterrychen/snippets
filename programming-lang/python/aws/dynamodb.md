## Usage
### [boto3 dynamodb document](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/dynamodb.html)

### Put a item

```
import boto3
client = boto3.client('dynamodb', region_name='us-west-2')
client.put_item(
    TableName='xxxxx',
    Item={
        'PrimaryKey': {'S': 'string'},
        'key2': {'N': 'number'}
    }
)
```

### List all a item (using scan for small table)

```
import boto3
client = boto3.client('dynamodb', region_name='us-west-2')
resp = client.scan(
    TableName='xxxxx',
    ConsistentRead=False
)

for i in resp['Items']):
    print(i)
```
