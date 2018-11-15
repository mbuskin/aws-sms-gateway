# aws-sms-gateway
AWS CloudFormation template to create an SMS Gateway using API Gateway, Lambda and SNS

## Purpose

This document provides a reference for all features available to you via the HTTPS interface for sending SMS.

The HTTP-API allows you to integrate your applications to the SMS Gateway API using the HTTPS protocol to send SMS.

The Client issues either a HTTP GET or POST request to the API interface supplying a list of required parameters.

The HTTP-API is used for one-way messaging only.

## Sending an SMS

The API URL is provided by the CloudFormation script on the output tab

## HTTP Parameters

| Parameter        | Description           | Mandatory  |
| ------------- |:-------------| -----:|
| sender      | Sender ID to use when sending the SMS message | Yes |
| msisdn      | MSIDSN of the recipient that the message will be sent to. Eg: +61412345678 or 61412345678      |   Yes |
| message | Message content to be sent      |    Yes |

## Example Request

https://<apiurl>/dev/sendsms?sender=Test&msisdn=+61412345678&message=Test