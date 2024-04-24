# Adding Global Tags to AWS Resources when deploying with AWS SAM

AWS SAM is an infrastructure-as-code approach to deploying CloudFormation stacks within AWS.

SAM adds a bit of entropy to the names of each resource created in order to avoid naming collisions. But how do you know which resources belong to which environment if the resource name doesn't include the environment? You can use tags on each resource. 

To tag all the resources in your stack with the environment, add a tags line to your `sam deploy` command.

```bash
sam deploy
      --stack-name ${ENV}-${AWS_STACK_NAME}
      --capabilities CAPABILITY_IAM
      --region ${AWS_DEFAULT_REGION}
      --s3-prefix ${ENV}-${AWS_STACK_NAME}
      --resolve-s3
      --no-fail-on-empty-changeset
      --tags 'Environment=${ENV} Project=DemoProject'
```

This will tag each resource created with your stack with the specified tags.

### References
* https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/sam-cli-command-reference-sam-deploy.html