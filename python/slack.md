# Slack

```
pip install slackclient
```


## [Slack API(official)](https://api.slack.com/methods)

## Call API by slackclient

```
import os
from slackclient import SlackClient

slack_token = os.environ["SLACK_API_TOKEN"]
sc = SlackClient(slack_token)

sc.api_call(
  "chat.postMessage",
  channel="C0XXXXXX",
  text="Hello from Python! :tada:"
)
```
