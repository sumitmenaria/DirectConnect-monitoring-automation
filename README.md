# DirectConnect-monitoring-automation

The CloudFormation template is configured to launch the following resources in your account for each region where you run it:
a) A lambda function which runs describe virtual-interfaces api call and picks up the BGP status of each of the VIF. Based on status value puts 0/1 on a custom metric in the namespace DirectConnectVif with the VIF name as dimension.
b) IAM Role for Lambda function which gives it the permissions to run the API calls mentioned in step-1
c)CloudWatch event rule which triggers the lambda function every 1 minute to update the metric.
