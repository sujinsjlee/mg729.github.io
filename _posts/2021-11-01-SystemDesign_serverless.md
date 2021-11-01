---
layout: post
title: Serverless
description: "Understanding concept of Serverless"
modified: 2021-11-01
tags: [System Design]
categories: [System Design]
---

## What is Serverless?

- **Serverless**
    - Serverless does not literally mean a backend *without a server*.
    - Serverless is Backend without server *MGMT (management)*
  
    - Serverless does not mean uploading the backend to the server
    - In serverless, the backend is divided into small function groups and uploaded to a server that you do not manage directly.
    - For example, AWS lambda
        - If it's not Serverless, the server is running 24/7.
        - Always ready to respond to requests
        - In the case of Serverless, the function you uploaded is sleeping. However, as soon as the request comes in, AWS will wake the function, perform the requested operation, and again the function will go to sleep.
    - The serverless revolution is exactly as above.
    - In other words, you don't have to stay awake for 24 hours.
    - In serverless, you only pay for the function you perform

## AWS Fargate

- **AWS Fargate.** 
  -  One example of serverless compute is **AWS Fargate.**  
  - AWS Fargate is a serverless compute platform that you can run either ECS or EKS on top of.  
  - Previously, you learned that ECS and EKS run on clusters of EC2 instances. And in that case, you are using EC2 as the compute platform for your containers, and you also have tight control over those instances.
  -  With AWS Fargate as the compute platform, you run your containers on a managed serverless compute platform. The scaling and fault-tolerance is built in and you don't need to worry about the underlying operating system or the environment. Instead, you just define your container, how you want your container to be run and then it scales on-demand.


## AWS Lambda
- [AWS Lamda](https://www.youtube.com/watch?v=t8sjTFM_tfE)

- **AWS Lambda function handler**
  
```python
def handler_name(event, context): 
    ...
    return some_value

def lamda_handler(event, context):
  print(event)
  return event['left'] + event['right']
```

- **trigger**
    - AWS Lambda functions work with existing AWS services.
    - ex) If you add a lambda function to the *AWS S3*, you can set the lambda function to be executed whenever a new file is uploaded to S3.
