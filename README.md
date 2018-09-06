# Setting up *Cognito* *App client settings* and *Domain name* with AWS CloudFormation

Forked from https://github.com/rosberglinhares/CloudFormationCognitoCustomResources

Converted to Serverless deployment method

This should be used as a template to implement Cognito custom resources within other projects, and should not be
deployed direcly - deployment will work, but it creates example Cognito resources, and is intended to serve as an example.

## Deploy steps

1. Install serverless

2. Navigate to the root directory

3. `cp serverless/LambdaCloudFormationCustomResource.yml ./serverless.yml`

4. `serverless deploy --stage STAGE --profile PROFILE`

5. `cp serverless/CognitoCloudFormationCustomResource.yml .serverless/yml`

6. `serverless deploy --stage STAGE --profile PROFILE`

## NOTE

* The order of deployments is *important* - the Lambda service must be deployed before the Cognito service, as the latter depends on cross-stack references to outputs from the former.

* Buildspec script examples (for integration with CodeBuild) are included in `./deploy/`