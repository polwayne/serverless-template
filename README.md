<!--
title: Serverless project template node.js
description: This is a template for creating serverless projects containing a Jenkins declarative Pipeline.
layout: Doc
-->
# Serverless Node Project

## API Gateway

This template contains the configuration for a single API-Gateway which is deployed separately. 

```
apiGateway:
    restApiId:
      'Fn::ImportValue': apiGateway-restApiId
    restApiRootResourceId:
      'Fn::ImportValue': apiGateway-rootResourceId
```

## Deploy

In order to deploy simply run

```bash
serverless deploy
```

## Build Pipeline

This template contains a Jenkins File defining a Build-Pipeline which deploys into different stages.

| Branch      | Environment |
|-------------|-------------|
| develop     | dev         |
| feature     | int         |
| master      | prod        |


