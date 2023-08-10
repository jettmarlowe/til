# Using CloudFormation with AWS ECS to Specify Secrets

I used CloudFormation when deploying a web application to AWS ECS (Elastic Cluster Service) via Fargate. This was easier than going in to the AWS console and setting up all the of components needed in the UI.  
  
Fargate allows the container to get secrets directly from Secrets Manager so the credentials don't need to be included in any repo files.  
  
However, it wasn't immediately clear to me how to specify the secret when it has multiple key-values under one secret name.

## Example Format
This example is for a secret with secret name "API_STUFF".  
The "API_STUFF" example secret has a key-value pair where the key is "API_BASE".  
As a short-cut, you can copy the secret ARN from the Console, and then append the key and then a double colon.


```yaml
    Secrets:
    - Name: API_BASE
    ValueFrom: "arn:aws:secretsmanager:region:aws_account_id:secret:API_STUFF-AbCdEf:API_BASE::"
``` 

The required format is 
```yaml
arn:aws:secretsmanager:region:aws_account_id:secret:secret-name:json-key:version-stage:version-id
```
In this example, since there isn't a "version-stage" or "version-id" value, just skip those values but still include the `:`.



# References
* https://stackoverflow.com/questions/75818349/unexpected-arn-format-with-parameters-when-trying-to-retrieve-asm-secret
* https://docs.aws.amazon.com/AmazonECS/latest/developerguide/secrets-envvar-secrets-manager.html