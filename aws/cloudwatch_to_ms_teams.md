# Sending AWS CloudWatch alarms into Microsoft Teams

It can be helpful to get alerts for CloudWatch alarms in a MS teams channel.
But it's not super straightforward to set up. 

Many other blogs have covered how to set up the AWS Lambda which triggers from the CloudWatch alarm being sent to the SNS Topic, and how to get the webhook connector set up in MS Teams.

However, I got tripped up in my Lambda code by `TypeError: string indices must be integers` 

I finally got the code working; turns out you need to add json.loads in order to parse the JSON from the original SNS message. 

The CloudWatch logs from testing the Lambda function were also vital for troubleshooting. Those are at Monitor -> Logs -> LogStream in the AWS Lambda Web UI.

```python
#!/usr/bin/python3.9
import json
import os
import logging
from urllib.request import Request, urlopen
from urllib.error import URLError, HTTPError

# Microsoft Teams url webhook
HOOK_URL = os.environ['WebhookURL']

logger = logging.getLogger()
logger.setLevel(logging.INFO)

def lambda_handler(event, context):

    message = json.loads(event['Records'][0]['Sns']['Message'])

    alarm_name = message['AlarmName']
    alarm_desc = message['AlarmDescription']
    new_state_value = message['NewStateValue']
    new_state_reason = message['NewStateReason']
    table_name = message['Trigger']['Dimensions'][0]['value']

    # format the message specifically for MS Teams 
    # this won't work for Slack
    teams_message = {
        "@type": "MessageCard",
        "@context": "https://schema.org/extensions",
        "themeColor": "0076D7",
        "title": "CloudWatch Alarm",
        "text": f"{new_state_value} on {table_name}",
        "sections": [
            {
                "facts": [
                    {
                        "name": "Alarm Name",
                        "value": f"{alarm_name}"
                    },
                    {
                        "name": "Alarm Desc ",
                        "value": f"{alarm_desc}"
                    },
                                        {
                        "name": "Value ",
                        "value": f"{new_state_value}"
                    },
                    {
                        "name": "Reason ",
                        "value": f"{new_state_reason}"
                    }
                ]
            }
        ]
    }
    
    request = Request(
        HOOK_URL,
        json.dumps(teams_message).encode('utf-8'))

    try:
        response = urlopen(request)
        response.read()
        logger.info("Message posted")
    except HTTPError as err:
        logger.error(f"Request failed: {err.code} {err.reason}")
    except URLError as err:
        logger.error(f"Server connection failed: {err.reason}")
```

### References
* https://aws.amazon.com/premiumsupport/knowledge-center/sns-lambda-webhooks-chime-slack-teams/
* https://stackoverflow.com/questions/70703606/string-indices-must-be-integers-error-when-parsing-aws-sns-response
* https://medium.com/@sebastian.phelps/aws-cloudwatch-alarms-on-microsoft-teams-9b5239e23b64
* https://4sysops.com/archives/aws-notifications-in-microsoft-teams/#Content-bal-title