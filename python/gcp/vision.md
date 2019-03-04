# Google Cloud Vision

```
pip install google-cloud-vision
```

Don't forget to set credential file path into `GOOGLE_APPLICATION_CREDENTIALS` environ var

## [API Document](https://googleapis.github.io/google-cloud-python/latest/vision/index.html)

## Moderation, Safe search detection
```
from google.cloud import vision

client = vision.ImageAnnotatorClient()

# uri 
image = vision.types.Image()
image.source.image_uri = uri

'''
# or binary
with io.open(path, 'rb') as image_file:
    content = image_file.read()
image = vision.types.Image(content=content)
'''

# Names of likelihood from google.cloud.vision.enums
# likelihood_name = ('UNKNOWN', 'VERY_UNLIKELY', 'UNLIKELY', 'POSSIBLE',
#                    'LIKELY', 'VERY_LIKELY')

response = client.safe_search_detection(image=image)
safe = response.safe_search_annotation
print(safe.adult, safe.medical, safe.spoof, safe.violence, safe.racy, sep=',')

# example result of print: 2, 1, 1, 1, 5
``` 

## [More snippets](https://github.com/GoogleCloudPlatform/python-docs-samples/blob/master/vision/cloud-client/detect/detect.py)
