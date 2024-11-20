# Week 0 — Billing and Architecture

## Turn on aws cli auto prompt
```
aws --cli-auto-prompt
```
## Get cli call identity
```
aws sts get-caller-identity 
```
```
aws sts get-caller-identity --query Account    
```
```
aws sts get-caller-identity --query Account --output text
```
## Get Account Contact Information
```
aws account get-contact-information
```
## Create Budget using cli
```
aws budgets create-budget --account-id 911167892485 --budget file://aws/json/budget.json --notifications-with-subscribers file://aws/json/budget-notifications-with-subscribers.json --profile harry
```
## Create SNS billing alarm
```
aws sns create-topic --name billing-alarm
```
##  Create cloud watch metric put alarm
```
aws cloudwatch put-metric-alarm --cli-input-json file://aws/json/alarm_config.json
```
