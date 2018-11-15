# aws-sms-gateway
AWS CloudFormation template to create an SMS Gateway using API Gateway, Lambda and SNS

## Purpose

This document provides a reference for all features available to you via the HTTPS interface for sending SMS.

The HTTP-API allows you to integrate your applications to the SMS Gateway API using the HTTPS protocol to send SMS.

The Client issues either a HTTP GET or POST request to the API interface supplying a list of required parameters.

The HTTP-API is used for one-way messaging only.

## API URL

The API URL generated is available on the output tab from within the AWS CloudFormation console.

## Sending an SMS

When sending a requests to the SMS API URL the below HTTP parameters are required in order for the message to be processed successfully.

### HTTP Parameters

| Parameter        | Description           | Mandatory  |
| ------------- |:-------------| -----:|
| senderid      | Sender ID to use when sending the SMS message | Yes |
| msisdn      | MSIDSN of the recipient that the message will be sent to. Eg: +61412345678 or 61412345678      |   Yes |
| message | Message content to be sent      |    Yes |

### Example Request

https://6ou9x3xgua.execute-api.ap-southeast-2.amazonaws.com/dev/sendsms?senderid=Test&msisdn=+61412345678&message=Test

## IAM Roles

As a part of the CloudFormation deployment two IAM roles are created, these roles in turn provide access to write logs through to CloudWatch and to permit access to publish to SNS. For production deployments it is recommended that you appropriately secure the roles down to least privilege as determined by the below table.

| ApiGatewayCloudWatchLogsRole | LambdaExecutionRole |
| ---------------------------- | ------------------- |
| logs:CreateLogGroup | sns:Publish |
| logs:CreateLogStream |  |
| logs:DescribeLogGroups |  |
| logs:DescribeLogStreams |  |
| logs:PutLogEvents |  |
| logs:GetLogEvents |  |
| logs:FilterLogEvents | |