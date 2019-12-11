## Usage
### [boto3 ec2 document](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/ec2.html)

### List spot requests with filters including Tags
```
import boto3

ec2 = boto3.client('ec2', region_name='region')
ec2.describe_spot_instance_requests(
    Filters=[
        {
            'Name': 'state',
            'Values': ['active']
        },
        {
            'Name': 'tag:xxxx',
            'Values': ["xxxx"]
        }
    ]
)['SpotInstanceRequests']
```
