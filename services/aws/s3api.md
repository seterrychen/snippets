## Usage
### checkout a file existing
```
$ aws s3api head-object --bucket www.codeengine.com --key index.html
{
    "AcceptRanges": "bytes",
    "ContentType": "text/html; charset=utf-8",
    "LastModified": "Sun, 08 Jan 2017 22:49:19 GMT",
    "ContentLength": 38106,
    "ContentEncoding": "gzip",
    "ETag": "\"bda80810592763dcaa8627d44c2bf8bb\"",
    "StorageClass": "REDUCED_REDUNDANCY",
    "CacheControl": "no-cache, no-store",
    "Metadata": {}
}

$ aws s3api head-object --bucket www.codeengine.com --key not_existing.txt
An error occurred (404) when calling the HeadObject operation: Not Found
```

### Get size of S3 Bucket
```
aws s3 ls --summarize --human-readable --recursive s3://bucket-name/directory
```
