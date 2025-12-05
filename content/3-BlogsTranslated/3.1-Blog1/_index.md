---
title: "Blog 1"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---


# Python 3.13 runtime is now available in AWS Lambda

by Julian Wood | on 14 NOV 2024 | in Announcements, AWS Cloud Development Kit, AWS Lambda, AWS SDK for Python, AWS Serverless Application Model, Python, Serverless | Permalink | Share

This post is written by Julian Wood, Principal Developer Advocate, and Leandro Cavalcante Damascena, Senior Solutions Architect Engineer.

AWS Lambda now supports Python 3.13 as a managed runtime and container base image. Python is a popular language for building serverless applications. The Python 3.13 release includes a number of changes to the language, implementation, and standard library. With this release, Python developers can now take advantage of these new features and improvements when creating serverless applications on Lambda. Python 3.13 also includes experimental support for some features, but these features are not available in Lambda.

You can develop Lambda functions in Python 3.13 using the AWS Management Console, AWS Command Line Interface (AWS CLI), AWS SDK for Python (Boto3), AWS Serverless Application Model (AWS SAM), AWS Cloud Development Kit (AWS CDK), and other infrastructure as code tools.

The Python 3.13 runtime allows you to implement serverless best practices using Powertools for AWS Lambda (Python). This is a developer toolkit that includes observability, batch processing, AWS Systems Manager Parameter Store integration, idempotency, feature flags, Amazon CloudWatch Metrics, structured logging, and more.

Lambda@Edge allows you to use Python 3.13 to customize low-latency content delivered through Amazon CloudFront.

## Lambda runtime changes

### Amazon Linux 2023

Like the Python 3.12 runtime, the Python 3.13 runtime is based on the provided.al2023 runtime, which is built on the Amazon Linux 2023 minimal container image. The Amazon Linux 2023 minimal image uses microdnf as the package manager, which is symlinked as dnf. This replaces the yum package manager used in Python 3.11 and earlier AL2-based images.

If you deploy your Lambda functions as container images, you must update your Dockerfiles to use dnf instead of yum when upgrading to the Python 3.13 base image from Python 3.11 or earlier base images.

Learn more about the provided.al2023 runtime in the blog post Introducing the Amazon Linux 2023 runtime for AWS Lambda and the Amazon Linux 2023 launch blog post.

## New Python features

### Data model improvements

There are improvements to the Python data model. _static_attributes_ stores the names of attributes accessed through self.X in any function in a class body.

### Typing changes

With the implementation of PEP 702, you can now use the new warnings.deprecated() decorator to mark deprecations in the type system and at runtime.

Python 3.13 also adds PEP 696, which introduces default values for type parameters. This improvement allows developers to specify default types for TypeVar, ParamSpec, and TypeVarTuple when omitting type arguments.

### Standard library

The standard library includes improvements for a new PythonFinalizationError exception, which is raised when an operation is blocked during finalization.

New functions base64.z85encode() and base64.z85decode() support encoding and decoding Z85 data.

The copy module now has a copy.replace() function, with support for many built-in types and any class that defines the _replace()_ method.

The os module has a suite of new functions for working with Linux timer notification file descriptors.

There is a change to the mutation semantics defined for locals().

## Unavailable experimental features

Python 3.13 includes some experimental features that are not enabled for Lambda managed runtime or base images. These features must be enabled when the Python runtime is compiled. Because the Lambda-provided Python 3.13 runtime is designed for production workloads, these features are not enabled in Lambda's build of Python 3.13 and cannot be enabled through execution-time flags.

To use these features in Lambda, you can deploy your own Python runtime using a custom runtime or container image with these features enabled.

### Free-threaded CPython

You cannot enable experimental support to run Python in free-threaded mode, with the global interpreter lock (GIL) disabled.

### Just-in-time (JIT) compiler

You also cannot enable the experimental JIT compiler in Lambda managed runtime or base image.

## Performance considerations

At launch, new Lambda runtimes receive less usage compared to existing established runtimes. This can lead to longer cold start times due to reduced cache residency in internal Lambda sub-systems. Cold start times are typically improved in the weeks following launch as usage increases.

Therefore, AWS recommends not drawing conclusions from performance comparisons side-by-side with other Lambda runtimes until performance has stabilized. Since performance depends heavily on the workload, customers with performance-sensitive workloads should conduct their own testing, rather than relying on general benchmark tests.

## Using Python 3.13 in Lambda

### AWS Management Console

To use the Python 3.13 runtime to develop your Lambda functions, specify the runtime parameter value as Python 3.13 when creating or updating a function.

Python version 3.13 is available in the Runtime dropdown on the Create Function page.

To update an existing Lambda function to Python 3.13, navigate to the function in the Lambda console and select Edit in the Runtime settings panel. The new Python version is available in the Runtime dropdown.

You may need to check your code and dependencies to ensure compatibility with Python 3.13, and update as necessary.

### AWS Lambda container image

Change the Python base image version by modifying the FROM statement in your Dockerfile.

```dockerfile
FROM public.ecr.aws/lambda/python:3.13
# Copy function code
COPY lambda_handler.py ${LAMBDA_TASK_ROOT}
```