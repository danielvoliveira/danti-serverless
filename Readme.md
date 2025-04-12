# Introduction

This project creates a microservice with serverless framework. The idea is just test this technology and map some commands by the get started instructions:

https://www.serverless.com/framework/docs/getting-started

# About structure

Inside <code>serverless.yml</code> we have all the properties that are settled in <code>aws</code>, like:

- <code>org</code>: organization name
- <code>app</code>: application name
- <code>service</code>: service name
- <code>provider</code>: used to specify Service-wide AWS-specific details
- <code>functions</code>: here we have AWS lambda functions

Inside <code>handler.js</code> we have the functions called through the lambda functions.

This files are the base of serverless and we have thousand of possibilities to construct microservices.

Use https://app.serverless.com/danti/apps to control and access the dashboard of application.

Use https://us-east-1.console.aws.amazon.com/console/home to access the AWS main website.

# Some commands:

Deploying will create/update cloud infrastructure and code on AWS, all at the same time. Use this when you make some change in some part of the application:

```sh
serverless deploy
```

Or you can deploy just a function to do this faster than deploy all system:

```sh
serverless deploy function -f my-api
```

This is the new dev command. In Serverless Framework V.4, It was create like a hybrid approach to development, to help developers develop rapidly with the accuracy of the real cloud environment.

```sh
serverless dev
```

To find URLs for your functions with API endpoints in the serverless, run:

```sh
deploy output
```
or

```sh
serverless info.
```

To invoke some function you can use:

```sh
sls invoke -f <function_name>
```

or

```sh
# Invoke and display logs:
serverless invoke -f <function_name> --log
```

You can invoke your function directly on local environment, to don't need deploy it all time to test, use:

```sh
sls invoke local -f <function_name>
```

This is a way to send params for your function while invoke it:

```sh
sls invoke local --function <function_name> --data '{"a":"bar"}'
```

You can use Serverless Framework to stream logs from AWS Cloudwatch directly to your terminal, use:

```sh
sls logs -f [Function name in serverless.yml] -t
```

If you want to delete your service, run remove. This will delete all the AWS resources created by your project and ensure that you don't incur any unexpected charges. It will also remove the service from Serverless Dashboard:

```sh
serverless remove
```

## Complete docs from Serverless:

https://www.serverless.com/framework/docs