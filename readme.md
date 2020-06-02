# Setup AWS Serverless Cognito with CloudFormation and Serverless Freamework (sls)

1. setup serverless freamework
```
npm install -g serverless
```

2. Configure your AWS credentials in serverless framework
You can set your credentials by applying command line:
```
serverless config credentials --provider aws --key AKIAIOSFODNN7EXAMPLE --secret wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
```
- You need to change the key and secret that you can get from AWS console --> IAM --> Users --> (select user) --> Security credentials --> Access keys

- Or you can set your default credentials to path ~/.aws/credentials

- You can overwrite the default credentials in .aws by adding -o to the command line with your new credentials

 - For more about how to configure AWS account check [here](https://www.serverless.com/framework/docs/providers/aws/guide/credentials/)

3. Generate AWS cloudFormation template. You can use the following command:
```
sls create --template aws-nodejs --name sls-cognito-backend
```
- You can change the runtime (e.g., node.js, python etc.) and the project name as well.

4. Edit your **serverless.yml** file and save it.

5. Deploy your infrastructure whenever you are ready
```
sls deploy -s [STAGE NAME] -r [REGION NAME] -v
```
- default STAGE NAME is **dev**
- default REGION NAME is **us-east-1**