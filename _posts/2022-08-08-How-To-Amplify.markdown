---
title:  "Creating an Amplify Project"
date:   2022-08-08 14:38:21 -0500
layout: 'post'
categories: [Amplify, Tips and Tricks]
tags: [aws, tutorial]
---

## Setting up a new Amplify Project ----TODO---- <br>
### This article will walk you through creating a new Amplify project
#### We will connect it to a React app, but you can choose to use any frontend framework of your choice
Pre-Requisites:
1. Registered AWS Account at [insert url here]
2. AWS CLI installed on your machine
&nbsp; You can install the command line tools using the below command. <br>
```npm i -g @aws-amplify/cli```

<br><br>
The next step is to configure and set up Amplify. <br>
```amplify configure```

If you are a new AWS user, this should ask you to create an IAM user to access your AWS account. If not, you can manually enter the details of the AWS account. 