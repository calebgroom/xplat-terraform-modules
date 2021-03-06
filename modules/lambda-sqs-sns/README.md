# lambda-sqs-sns

Puts an SQS queue between an SNS topic and a lambda.

Use this if you would otherwise have a lambda consuming from an SNS topic but don't want to risk losing any messages.

The SQS queue will instead consume messages from the SNS topic and then automatically deliver them to the lambda. If the lambda fails to process them, they will be sent to a dead letter queue which is also created by this module.

## Variables

* sns_arn - The SNS topic you want to read messages from.

* lambda_arn - The lambda you want to direct messages to.

* name - Used, along with `stage`, to create the name of the main queue and the dead letter queue. Also used for some tags.

* stage - See `name`.
