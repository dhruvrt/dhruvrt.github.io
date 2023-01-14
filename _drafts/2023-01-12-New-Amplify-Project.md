---
title:  "Creating an Amplify Project 2"
date:   2023-01-12 08:24:33 -0500
layout: 'post'
categories: [Amplify, Tips and Tricks]
tags: [aws, tutorial]
---

# Setting up a new Amplify Project

## This article will walk you through creating a new Amplify project

### We will connect it to a React app, but you can choose to use any frontend framework of your choice.

## Pre-Requisites:

At this point, I already have an AWS account, AWS CLI set up on my machine, and Amplify configured to my IAM default credentials - 

[Create and activate an AWS account](https://aws.amazon.com/premiumsupport/knowledge-center/create-and-activate-aws-account/)

Register a new AWS Account

```bash
npm i -g @aws-amplify/cli
```

```bash
amplify configure
```

---

## Creating an app -

In an empty directory, 

```bash
npx create-react-app my_new_app
```