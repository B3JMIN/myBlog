+++
title = "Learn AWS Lambda"
date = "2020-04-11"
author = "Benjamin Cai"
description = "How I learn AWS service and Lambda"
showFullContent = false
+++


## Start learning Lambda and AWS for the first time with Nodejs ## 

### What can Lambda do? ###
AWS Lambda is a serverless compute(It allows you to run code without having to deal with servers in the cloud) service that runs code and automatically manages the underlying compute resources with all the AWS services 

P.S. This is what I am interested in right now && Not Familiar with AWS neither

### Implete with Node.js 
```javascript

exports.handler =  async function(event, context) {
  console.log("EVENT: \n" + JSON.stringify(event, null, 2))
  return context.logStreamName
}
```

This is a async function in nodejs, use `handler` to process event, once the handler exits or returns a response, it becomes available to handle another event.

There are three parameters inteh `handler` function:
1. `event` contains information from the invoker, the `invoke` is a JSON-formatted string 
2. `context` contains information about the invocation, function
3. `callback` is a function that you can call in non-async [handler](https://docs.aws.amazon.com/lambda/latest/dg/nodejs-handler.html#nodejs-handler-sync) to send a response

The `console.log` can log the JSON format of event or return `null`

