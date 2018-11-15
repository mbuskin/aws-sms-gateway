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