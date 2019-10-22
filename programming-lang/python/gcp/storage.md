# Google Cloud Storage

```
pip install google-cloud-storage
```

Don't forget to set credential file path into `GOOGLE_APPLICATION_CREDENTIALS` environ var

## [API Document](https://googleapis.github.io/google-cloud-python/latest/storage/index.html)

## download file

```
"""Downloads a blob from the bucket."""
storage_client = storage.Client()
bucket = storage_client.get_bucket(bucket_name)
blob = bucket.blob(source_blob_name)
blob.download_to_filename(destination_file_name)
```

## Using prefix to list blobs

```
"""Lists all the blobs in the bucket."""
storage_client = storage.Client()
bucket = storage_client.get_bucket(bucket_name)

blobs = bucket.list_blobs()

for blob in blobs:
    print(blob.name)
``` 

## [More snippets](https://github.com/googleapis/google-cloud-python/tree/master/storage/google/cloud/storage)
