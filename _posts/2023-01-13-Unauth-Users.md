---
title:  "AWS Amplify/AppSync - Unauth Flow"
date:   2023-01-13 10:04:07 -0500
layout: 'post'
categories: [Amplify, Tips and Tricks]
tags: [aws, tutorial]
toc: false
---

# Amplify AppSync APIs for unauthenticated users

<aside>
<img src="https://www.notion.so/icons/code_yellow.svg" alt="https://www.notion.so/icons/code_yellow.svg" width="20px" /> <b>how to give limited API access (only read) to unauthenticated users </b>
</aside>

### Pre-requisites -

Amplify project already set up with AppSync API. You can do this by running `$ amplify add api` in your shell. 

Here’s my graphql schema for a basic Todo app. You can generate this by selecting the basic todo application option in the amplify command interface.

![GraphQL Schema](/assets/images/graphql_schema_default.png){: height: "1000"}

### Adding Authentication to your Project
Run the below command in your project directory's root and follow the instructions for the Auth flow. _make sure to choose "yes" for "Allow unauthenticated logins?"_

```bash
$ amplify add auth
```
![Auth Interface](/assets/images/amplify_add_auth_flow.png)
_`amplify add auth` flow_


Now, this should create a cognito user and identity pool for your project. 

**Modifying unauth role in IAM**

1. Navigate to the specific IAM unauth roles in the AWS IAM console.
2. Edit the role to add a read only policy like below 

![unauth role](/assets/images/unauth_role_policy.png)
_unauth role policy in IAM console._
    

**Modifying your graphQL schema**

In your project directory, navigate to the graphql schema (_”/yourProjectDirectory/Amplify/backend/schema.graphql”_)

add the @aws-iam directive to the table for which you want to restrict read only access for unauthenticated users.

![graphql schema @iam](/assets/images/graphql_schema_iam_directive.png)
_GraphQL Schema_

**Modifying aws-exports.js file**

In your aws-exports.js file, make sure to change the “aws_appsync_authenticationType” key to have the value “AWS_IAM”

```
const awsmobile = {
    "aws_project_region": "us-east-1",
    "aws_cognito_identity_pool_id": "removed_for_privacy",
    "aws_cognito_region": "us-east-1",
    "aws_user_pools_id": "removed_for_privacy",
    "aws_user_pools_web_client_id": "removed_for_privacy",
    "oauth": {},
    "aws_cognito_username_attributes": [],
    "aws_cognito_social_providers": [],
    "aws_cognito_signup_attributes": [
        "EMAIL"
    ],
    "aws_cognito_mfa_configuration": "OFF",
    "aws_cognito_mfa_types": [
        "SMS"
    ],
    "aws_cognito_password_protection_settings": {
        "passwordPolicyMinLength": 8,
        "passwordPolicyCharacters": []
    },
    "aws_cognito_verification_mechanisms": [
        "EMAIL"
    ],
    "aws_appsync_graphqlEndpoint": "https://removed_for_privacy.appsync-api.us-east-1.amazonaws.com/graphql",
    "aws_appsync_region": "us-east-1",
    "aws_appsync_authenticationType": "AWS_IAM",
    "aws_appsync_apiKey": "removed_for_privacy"
};
```

That’s it! I hope...