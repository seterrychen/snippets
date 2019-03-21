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

## Adding attachment

```
attachment = [
    {
        "text": "Choose an action",
        "fallback": "You are unable to choose an option",
        "callback_id": "lunch_intro",
        "color": "#3AA3E3",
        "attachment_type": "default",
        "actions": [
            {
                "name": "enroll",
                "text": "Enroll",
                "type":"button",
                "value":"enroll"
            },
            {
                "name": "leave",
                "text": "Leave",
                "type": "button",
                "value": "leave"
            }
        ]
    }
]

sc.api_call("chat.postMessage", channel=channel, text="What would you like to do?", attachments=json.dumps(attachment))
```
