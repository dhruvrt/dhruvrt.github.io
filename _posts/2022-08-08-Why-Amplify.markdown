---
title:  "Why Amplify?"
date:   2022-08-08 14:38:21 -0500
categories: [Amplify, About]
layout: 'post'
tags: [aws]
pin: true
---

## This is a blog on why we chose AWS Amplify over other options, its advantages and disadvantages, and how to set up a simple Amplify Project.

### Advantages - 
Overall, Amplify is a comprehensive platform that provides a range of tools and services for building and deploying cloud-powered applications. Its ease of use, scalability, and customization make it a popular choice among developers looking to build cloud-based applications on AWS.
* Amplify is a cloud-based development platform that simplifies the process of building and deploying cloud-powered applications. It provides a set of tools, libraries, and services that allow developers to easily build, deploy, and manage cloud-based applications.

* One of the key benefits of Amplify is its ability to quickly spin up a variety of cloud services, including back-end APIs, data stores, and serverless functions. This can save developers time and effort in the early stages of development, allowing them to focus on building the core features of their application.

* Amplify also provides a range of tools and services for testing, debugging, and monitoring cloud-based applications. This can help developers ensure that their applications are performing optimally and resolve any issues that may arise.

* In addition to its development and deployment capabilities, Amplify also provides a number of resources and best practices for building cloud-based applications. This includes documentation, tutorials, and a community forum where developers can ask questions and share knowledge with their peers.


### Disadvantages - 
1. AWS Amplify is a fairly new service and is still in development. So it is going through constant changes.
2. High learning curve compared to other alternatives

### Options for building and deploying cloud-powered applications - 
#### AWS CloudFormation
This is a service that helps you model and set up your Amazon Web Services resources so you can spend less time managing infrastructure and more time building applications.

#### Azure Resource Manager
This is a service from Microsoft Azure that enables you to deploy, manage, and monitor all of the resources for your solution in a single, coordinated operation.

#### Google Cloud Deployment Manager
This is a service from Google Cloud that helps you define, create, and manage Google Cloud Platform resources using templates written in YAML.

#### Terraform
This is an open-source tool that enables you to write, plan, and create infrastructure as code across a variety of cloud providers, including AWS, Azure, and Google Cloud Platform.

#### Serverless Framework
This is an open-source, framework-agnostic tool that allows you to build and deploy serverless applications on a variety of cloud providers, including AWS, Azure, and Google Cloud Platform.


### Why Amplify specifically for me?

<br> Amplify is specifically designed to work with AWS and the Amazon Web Services ecosystem, while the other options listed above are more general-purpose and can work with a variety of cloud providers.<br>

When we started development on our project, we had limited experience in full stack development. However, we had previously used AWS DynamoDB and Lambda on our Movie Recos project, so we were familiar with those technologies. After considering our options, we decided to use Amplify to integrate the required AWS services into our project. We were pleased to find that Amplify not only facilitated the connection between DynamoDB and AppSync GraphQL APIs, but also provided integrations with Elasticsearch for accurate music and song data matching. Additionally, Amplify made it easy for us to configure authentication and UI integration. Overall, Amplify proved to be a valuable tool due to its ability to seamlessly integrate with our project and its scalability and customization capabilities.

To summarize - 
1. Familiar with some of the technology already.
2. Integration with this technology was very easy and quick - specifically DDB, Appsync, Opensearch, Lambdas
3. Scalability and customization to our needs.
4. Easy authentication and UI integration.