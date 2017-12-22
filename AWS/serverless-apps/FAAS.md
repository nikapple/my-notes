# AWS Lambda : Functions as a Service
- [serverless-framework](https://serverless.com/framework/docs/providers/aws/guide/functions/)
- [spring-boot-lambda](https://www.rowellbelen.com/serverless-microservices-with-spring-boot-and-spring-data/)
- AWS Lambda functions can only be invoked/triggered via another AWS service
- Serverless
  - servers are abstracted away from end users
  - servers are managed by cloud provider
  - no infra management
- microservices - 1 function - 'n' related jobs
  - breaks app down into individual functions that are deployed
- Response should follow particular **format** to pass through AWS API Gateway proxy

###### Triggering Lambda functions
- Invocation Types
  - Request - Response
  - Event
  - Dry run

### Creating a Restful API
- install serverless framework `npm install -g serverless`
- AWS API Gateway
- AWS Lambda functions should be state independent
- Store state in DynamoDb
- push - pull , sync - async
- The first thing to do when using the Serverless Framework is to create a **serverless.yaml , env.yml**
