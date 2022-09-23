# Useful commands

- `node register_commands/register.js` register slash commands with Discord - if Guild ID isn't present in .env, these will be deployed globally
- `sam build && sam deploy --guided` deploys the bot to AWS Lambda
- `node generate_template/generate.js` generates a CloudFormation template for the bot
- `node generate_template/generate.js && \ node register_commands/register.js && \ sam build && sam deploy` deploys the bot after you add new commands to `src/modules/example/`
  `sam destroy` cleans up

# Troubleshooting

Can't deploy?

```
aws configure list
nano ~/.aws/credentials
```

Make sure there is a mfa profile in the credentials file. If not, add one that looks like this:

```
[mfa]
aws_access_key_id = <VALUE>
aws_secret_access_key = <VALUE>
aws_session_token = <VALUE>
```

Then run the mfa script:

```
sh mfa.sh <MFA_CODE>
```

# Notes

This project contains source code and supporting files for a serverless application that you can deploy with the AWS Serverless Application Model (AWS SAM) command line interface (CLI). It includes the following files and folders:

- `src` - Code for the application's Lambda function.
- `events` - Invocation events that you can use to invoke the function.
- `__tests__` - Unit tests for the application code.
- `template.yaml` - A template that defines the application's AWS resources.

Resources for this project are defined in the `template.yaml` file in this project. The file has its own template generator. You can update the template to add AWS resources through the same deployment process that updates your application code.
