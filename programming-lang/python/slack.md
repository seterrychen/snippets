# Slack

## python-slackclient

```
pip install slackclient
```


### [Slack API(official)](https://api.slack.com/methods)

### Call API by slackclient
#### 2.x version

```
import os
import slack

slack_token = os.environ["SLACK_API_TOKEN"]
sc = slack.WebClient(token=slack_token)

sc.chat_postMessage(
  channel="#random',
  text="Hello from Python! :tada:"
)
```

#### 1.x version

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

### Adding attachment
#### 2.x version

```
sc.chat_postMessage(
  channel="#random',
  text="What would you like to do?"
  attachments=json.dumps(attachment)
)
```

#### 1.x version

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


## Using Requests to send message to incoming message
```
def send_slack_msg(msg):
    hook_url = "https://xxxxxx"
    text = {'text': msg}
    requests.post(
        hook_url,
        data=json.dumps(text),
        headers={'Content-Type': 'application/json'}
    )
```

### metion user or channel
```
msg = '<@userid@> xxxxxxx'
```
