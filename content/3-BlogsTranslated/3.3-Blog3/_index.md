---
title: "Blog 3"
date: 2025-09-09
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---


# Accelerating data science innovation: How Bayer Crop Science uses AWS AI/ML services to build their next-generation MLOps service

by Lance Smith, Jake Malmad, Karthik Prabhakar, Kenton Blacutt, and Nicole Brown on 08 JUL 2025 in Amazon API Gateway, Amazon EventBridge, Amazon Q, Amazon Q Business, Amazon Q Developer, Amazon SageMaker, Amazon SageMaker Data & AI Governance, Artificial Intelligence, Customer Solutions, Generative AI | Permalink | Comments | Share

The world's population is growing at a rapid pace. The growing global population requires innovative solutions to produce food, fiber, and fuel, while restoring natural resources like soil and water and addressing climate change. Bayer Crop Science estimates that farmers need to increase crop yields by 50% by 2050 to meet these demands. To support their mission, Bayer Crop Science is partnering with farmers and partners to promote and scale regenerative agriculture—a future where farming can produce more while restoring the environment.

Regenerative agriculture is a sustainable farming philosophy aimed at improving soil health by integrating nature to create healthy ecosystems. It's based on the idea that agriculture should restore degraded land and reverse degradation, rather than maintaining current conditions. The Crop Science division at Bayer believes that regenerative agriculture is the foundation for the future of farming. Their vision is to produce 50% more food by restoring nature and scaling regenerative agriculture. To make this mission a reality, Bayer Crop Science is accelerating model training with Amazon SageMaker and speeding up code documentation with Amazon Q.

In this post, we present how Bayer Crop Science manages large-scale data science operations by training models for their data analysis needs and maintaining high-quality code documentation to support developers. Through these solutions, Bayer Crop Science expects to reduce developer onboarding time by up to 70% and improve developer productivity by up to 30%.

## The challenge

Bayer Crop Science faced the challenge of scaling genomic prediction models to accelerate time to market. The company also needed data scientists to focus on building high-value foundation models (FMs), rather than worrying about building and designing solutions. Before building their Decision Science Ecosystem solution, provisioning a data science environment could take many days for a data team within Bayer Crop Science.

## Solution overview

Bayer Crop Science's Decision Science Ecosystem (DSE) is a next-generation machine learning operations (MLOps) solution built on AWS to accelerate data-driven decision-making for data science teams at scale across the organization. AWS services support Bayer Crop Science in creating a connected decision-making system accessible to thousands of data scientists. The company is using the solution for generative AI, advances in product pipeline, geospatial image analysis of field data, and large-scale genomic prediction models that will enable Bayer Crop Science to become more data-driven and accelerate time to market. This solution supports data scientists at every step, from idea to model output, including the complete record of business decisions made using DSE. Other divisions within Bayer are also beginning to build a similar solution on AWS based on DSE's success.

Bayer Crop Science teams' DSE integrates seamlessly with SageMaker, a fully managed service that enables data scientists to quickly build, train, and deploy machine learning (ML) models for different use cases so they can make data-driven decisions quickly. This drives collaboration within Bayer Crop Science between product supply, R&D, and commercial. Their data science strategy no longer requires self-service data engineering, but instead provides an efficient resource to drive fast data engineering at scale. Bayer Crop Science chose SageMaker because it provides a single cohesive experience where data scientists can focus on building high-value models, without having to worry about building and designing that resource itself. With the help of AWS services, cross-functional teams can quickly align to reduce operational costs by minimizing redundancy, addressing errors early and often, and quickly identifying issues in automated workflows. The DSE solution uses SageMaker, Amazon Elastic Kubernetes Service (Amazon EKS), AWS Lambda, and Amazon Simple Storage Service (Amazon S3) to accelerate innovation at Bayer Crop Science and create a seamless, customized end-to-end user experience.

The following diagram illustrates the DSE architecture.

## Solution walkthrough

Bayer Crop Science had two main challenges in managing large-scale data science operations: maintaining high-quality code documentation and optimizing existing documentation across multiple repositories. With Amazon Q, Bayer Crop Science addressed both challenges, helping them onboard developers faster and improve developer productivity.

The company's first use case focused on automatically generating high-quality code documentation. When a developer pushes code to a GitHub repository, a webhook—a lightweight, event-driven communication that automatically sends data between applications using HTTP—triggers a Lambda function through Amazon API Gateway. This function then uses Amazon Q to analyze code changes and generate comprehensive documentation as well as change summaries. The updated documentation is then stored in Amazon S3. The same Lambda function also creates a pull request with an AI-generated summary of code changes. To maintain security and flexibility, Bayer Crop Science uses Parameter Store, a capability of AWS Systems Manager, to manage prompts for Amazon Q, allowing quick updates without redeployment, and AWS Secrets Manager to securely handle repository tokens.

This automation significantly reduces the time developers spend creating documentation and pull request descriptions. The generated documentation is also fed into Amazon Q, so developers can quickly answer questions they have about a repository and onboard into projects.

The second use case addresses the challenge of maintaining and improving the quality of existing code documentation. An AWS Batch job, triggered by Amazon EventBridge, processes code repositories. Amazon Q generates new documentation for each code file, which is then indexed along with the source code. The system also creates high-level documentation for each module or function and compares AI-generated documentation with existing human-written documentation. This process allows Bayer Crop Science to systematically evaluate and enhance their documentation quality over time.

To improve searchability, Bayer Crop Science added repository names as custom attributes in the Amazon Q index and prefixed them to indexed content. This improvement enhances the accuracy and relevance of documentation searches. The development team also implemented strategies to handle API throttling and variability in AI responses, maintaining robustness in the production environment. Bayer Crop Science is considering developing a management plane to streamline adding new repositories and centralize management of settings, tokens, and prompts. This will continue to enhance the system's scalability and ease of use.

Organizations wanting to replicate Bayer Crop Science's success can implement similar webhook-triggered documentation generation, use Amazon Q Business for both documentation generation and quality evaluation, and integrate the solution with existing version control and code review processes. By using AWS services like Lambda, Amazon S3, and Systems Manager, companies can create a scalable and manageable architecture for their documentation needs. Amazon Q Developer also helps organizations further accelerate their development timelines by providing real-time code suggestions and a next-generation chat experience built-in.

"One of the lessons we've learned over the past 10 years is that we want to write less code. We want to focus our time and investment only on things that bring differential value to Bayer, and we want to leverage everything that AWS provides out of the box. Part of our goal is to reduce the development cycles needed to move a model from proof-of-concept stage, to production, and finally to business adoption. That's where the value is."

– Will McQueen, VP, Head of CS Global Data Assets and Analytics at Bayer Crop Science.

## Conclusion

Bayer Crop Science's approach aligns with modern MLOps practices, enabling data science teams to focus more on high-value modeling tasks rather than time-consuming documentation processes and infrastructure management. By adopting these practices, organizations can significantly reduce the time and effort required for code documentation while improving overall code quality and team collaboration.

Learn more about Bayer Crop Science's generative AI journey, and explore how Bayer Crop Science is redesigning sustainable practices through advanced technology.

## About Bayer

Bayer is a global enterprise with core competencies in the life science fields of healthcare and nutrition. In line with its mission, "Health for all, Hunger for none," the company's products and services are designed to help people and the planet thrive by supporting efforts to understand the major challenges posed by growing and aging global populations. Bayer is committed to driving sustainable development and creating a positive impact with its business activities. At the same time, Bayer aims to increase its earning power and create value through innovation and growth. The Bayer brand represents trust, reliability, and quality worldwide. In fiscal year 2023, the Group had approximately 100,000 employees and had sales of 47.6 billion euros. R&D expenses before special items amounted to 5.8 billion euros. For more information, visit www.bayer.com.

## About the authors

**Lance Smith** is a Senior Solutions Architect and is part of the global Healthcare and Life Sciences industry division at AWS. He has spent the past 2 decades helping life sciences companies adopt technology to pursue their mission of helping their patients. Outside of work, he enjoys traveling, hiking, and spending time with family.

**Kenton Blacutt** is an AI Consultant in the Amazon Q Customer Success team. He works directly with customers, helping them solve real business problems with cutting-edge AWS technologies. In his free time, he enjoys traveling and occasionally running marathons.

**Karthik Prabhakar** is a Senior Applications Architect in the AWS Professional Services team. In this role, he collaborates with customers to design and implement cutting-edge solutions for their critical business systems, focusing on areas like scalability, reliability, and cost optimization in digital transformation and modernization projects.

**Jake Malmad** is a Senior DevOps Consultant in the AWS Professional Services team, specializing in infrastructure as code, security, containers, and orchestration. As a DevOps consultant, he uses this expertise to collaborate with customers, designing and implementing solutions for automation, scalability, reliability, and security across various types of cloud adoption and transformation projects.

**Nicole Brown** is a Senior Engagement Manager in the AWS Professional Services team based in Minneapolis, MN. With over 10 years of professional expertise, she has led cross-functional, global teams in the healthcare and life sciences industries. She is also an advocate for women in technology and currently holds a board position in the Women at Global Services affinity group.