# Enes's Millennium Age Carousel Website deployed on AWS CloudFront, S3 and Route 53 using CloudFormation

## Description

Enes's Millennium Age Carousel is a static website application deployed on AWS Simple Storage Service (S3), served through CloudFront and Route 53 using AWS CloudFormation Service.

## Project Architecture

![project-details](./readme/project.png)

## CloudFormation Stack

![Template](./readme/template-designer.png)

- Your company has recently started a web application project that will serve as an attraction point for pet lovers. As a first step of the project, you have deployed the app on EC2 instance and showed that design is good and working, thus you can go to next step. Developers in your team have prepared Enes carousel application and pushed necessary files for the project to the repository on Github.

- Your task is to deploy the application as static web page in the production environment. Thus, you need to deploy the web application using the `index.html` and an images given within the `static-web` folder. Note the followings for your web application.

  - User should face first with `index.html` when web app started.

  - Application should be deployed on AWS S3 as static website.

  - Application should be served to public through domain name of the company using AWS CloudFront and Route 53. Thus, you need to prepare a CloudFormation template with following configurations;

    - The application stack should be created with new AWS resources.

    - The application stack should take two parameters from the user;

      - The DNS name of an existing Amazon Route 53 hosted zone e.g. `enes.com`

      - The full domain name e.g. `turan.enes.com` for the web application

    - The Web Application files should be served from S3 bucket which should be configured as a static website host and the content should be reachable from anywhere.

    - CloudFront should be set as a cache server which points to S3 bucket of the web app with following configurations;

      - The CloudFront distribution should be connected to the full domain name of the application.

      - The CloudFront distribution should communicate with S3 bucket securely.

      - The CloudFront distribution should default to `index.html`.

      - HTTP version 2 should be employed.

      - As cache behavior;

        - `GET` and `HEAD` methods should be allowed.

        - Cookies should not be forwarded to bucket.

        - All request should be redirected to HTTPS.

        - Newly created ACM Certificate should be used for securing connections.

    - Within Route 53 a record set should be configured to send requests to the CloudFront distribution.

    - After the stack created, following outputs should be given;

      - Full DomainName of Enes Carousel Application

      - Endpoint for Enes CloudFront Distribution

      - Name of S3 Bucket for Enes Website

  - The Application files should be uploaded to the application S3 bucket from local git repo using AWS CLI commands.

# Expected CloudFormation Outputs

![outputs](./readme/cfoutputs.png)

## Certificate Manager Output

![certificate-manager](./readme/certificate.png)

## S3 Bucket Output

![S3-bucket](./readme/s3bucket_output.png)

## CloudFront Distribution Output

![cloudfront](./readme/cloudfront.png)

![cloudfront-output](./readme/CloudfrontEndpoint.png)

## Domain Name Output

![Domain](./readme/FullDomainName.png)

### At the end of the project, following topics are to be covered;

- Static Website Deployment

- Bash scripting

- AWS Simple Storage Service

- AWS CloudFront Distribution

- AWS Certificate Manager

- AWS Route 53 Service

- AWS CloudFormation Service

- AWS CloudFormation Template Design

- Git & Github for Version Control System

### At the end of the project, you will be able to;

- demonstrate bash scripting skills using AWS CLI to upload the application files to S3 bucket.

- configure S3 buckets through CloudFormation.

- configure ACM Certificate through CloudFormation.

- configure CloudFront through CloudFormation.

- configure Route 53 record set through CloudFormation.

- configure CloudFormation template to use AWS Resources.

- use AWS CloudFormation Service to launch stacks.

- use git commands (push, pull, commit, add etc.) and Github as Version Control System.

## Resources

- [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)

- [AWS CLI Command Reference](https://docs.aws.amazon.com/cli/latest/index.html)

- [NFT Templates](https://www.silks.io/)
