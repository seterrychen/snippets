# Slack

## Installation
```
$ pip install slack_sdk
```

## Usage Note
* Before Slack Bot sending message to private channel, the bot should be invited by command `/invite @BotName` with `chat:write` permission


## [Slack API(official) Document](https://api.slack.com/methods)
## Examples
### Sending a message to Slack
```
import os
from slack_sdk import WebClient
from slack_sdk.errors import SlackApiError

client = WebClient(token=os.environ['SLACK_BOT_TOKEN'])

try:
    response = client.chat_postMessage(channel='#random', text="Hello world!")
    assert response["message"]["text"] == "Hello world!"
except SlackApiError as e:
    # You will get a SlackApiError if "ok" is False
    assert e.response["ok"] is False
    assert e.response["error"]  # str like 'invalid_auth', 'channel_not_found'
    print(f"Got an error: {e.response['error']}")
```
