---
title: "Blog 2"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---


# Implementing custom domain names for private endpoints with Amazon API Gateway

by Chris McPeek | on 21 NOV 2024 | in Amazon API Gateway, Amazon EC2, Amazon Elastic Container Service, Amazon Elastic Kubernetes Service, AWS Lambda, Resource Access Manager (RAM), Serverless | Permalink | Share

This post is written by Heeki Park, Principal Solutions Architect  
1/23/25: This post has been updated to correct the AWS CloudFormation templates.

Amazon API Gateway is introducing custom domain name support for private REST API endpoints. Customers choose private REST API endpoints when they want endpoints that can only be invoked from within their Amazon VPC. Custom domain names are simpler and more intuitive URLs that you can use with your application and were previously only supported with public REST API endpoints. Now you can use custom domain names to map to private REST APIs and share those custom domain names across accounts using AWS Resource Access Manager (AWS RAM).

## Overview of API Gateway connectivity

When considering network connectivity with API Gateway, there are two important aspects to note: integration type and connectivity type. The following diagram shows examples of those considerations.

Figure 1: Overall architecture

The first aspect is the distinction between frontend integrations and backend integrations. Frontend integrations are how API clients such as mobile devices, web browsers, or client applications connect to the API endpoint. Backend integrations are the API services that your API Gateway endpoint proxies requests to, such as applications running on Amazon Elastic Compute Cloud (EC2) instances, Amazon Elastic Kubernetes Service (EKS) or Amazon Elastic Container Service (ECS) containers, or as AWS Lambda functions. The second aspect is whether that connection goes through the public internet or through your private VPC.

## Invoking private REST API endpoints

To send requests to a private REST API endpoint, clients must operate in a VPC configured with a VPC endpoint. When the VPC endpoint is configured, a client has three different options in the VPC to connect to the API endpoint, depending on how the VPC and VPC endpoint are configured.

If the VPC endpoint has private DNS enabled, the client can send requests to the standard endpoint URL: https://{api-id}.execute-api.{region}.amazonaws.com/{stage}. These requests will resolve to the VPC endpoint, which is then routed to the appropriate API Gateway endpoint.

Figure 2: VPC endpoint configured with private DNS names enabled

Alternatively, if the VPC endpoint has private DNS disabled, the client can send requests to the VPC endpoint URL: https://{vpce-id}.execute-api.{region}.amazonaws.com/{stage}. One of the following headers also needs to be sent with that request.  
Host: {api-id}.execute-api.us-east-1.amazonaws.com  
x-apigw-api-id: {api-id}

Finally, if the VPC endpoint has private DNS disabled and the private REST API endpoint is associated with the VPC endpoint, the client can send requests to the following URL: https://{api-id}-{vpce-id}.execute-api.{region}.amazonaws.com/{stage}. To associate a VPC endpoint with a private API, the following property configures that association.

```yaml
     EndpointConfiguration:
        Type: PRIVATE
        VPCEndpointIds:
          - !Ref vpcEndpointId
```