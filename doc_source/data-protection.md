# Data protection in EC2 Image Builder<a name="data-protection"></a>

The AWS [shared responsibility model](http://aws.amazon.com/compliance/shared-responsibility-model/) applies to data protection in EC2 Image Builder\. As described in this model, AWS is responsible for protecting the global infrastructure that runs all of the AWS Cloud\. You are responsible for maintaining control over your content that is hosted on this infrastructure\. This content includes the security configuration and management tasks for the AWS services that you use\. For more information about data privacy, see the [Data Privacy FAQ](http://aws.amazon.com/compliance/data-privacy-faq)\. For information about data protection in Europe, see the [AWS Shared Responsibility Model and GDPR](http://aws.amazon.com/blogs/security/the-aws-shared-responsibility-model-and-gdpr/) blog post on the *AWS Security Blog*\.

For data protection purposes, we recommend that you protect AWS account credentials and set up individual user accounts with AWS Identity and Access Management \(IAM\)\. That way each user is given only the permissions necessary to fulfill their job duties\. We also recommend that you secure your data in the following ways:
+ Use multi\-factor authentication \(MFA\) with each account\.
+ Use SSL/TLS to communicate with AWS resources\. We recommend TLS 1\.2 or later\.
+ Set up API and user activity logging with AWS CloudTrail\.
+ Use AWS encryption solutions, along with all default security controls within AWS services\.
+ Use advanced managed security services such as Amazon Macie, which assists in discovering and securing personal data that is stored in Amazon S3\.
+ If you require FIPS 140\-2 validated cryptographic modules when accessing AWS through a command line interface or an API, use a FIPS endpoint\. For more information about the available FIPS endpoints, see [Federal Information Processing Standard \(FIPS\) 140\-2](http://aws.amazon.com/compliance/fips/)\.

We strongly recommend that you never put confidential or sensitive information, such as your customers' email addresses, into tags or free\-form fields such as a **Name** field\. This includes when you work with Image Builder or other AWS services using the console, API, AWS CLI, or AWS SDKs\. Any data that you enter into tags or free\-form fields used for names may be used for billing or diagnostic logs\. If you provide a URL to an external server, we strongly recommend that you do not include credentials information in the URL to validate your request to that server\.

## Encryption and key management in EC2 Image Builder<a name="image-builder-enrcyption"></a>

Image Builder encrypts data in transit and at rest by default\. Custom components defined in the service can be added to your image pipelines and shared with other customer accounts\. You are not required to share your components to build images\. 

Custom components are encrypted with your KMS key or a KMS key owned by Image Builder\. Image Builder does not store any of your logs in the service\. All logs are saved on your Amazon EC2 instance that is used to build the image, or in your Systems Manager automation logs\. 

You can manage your keys through AWS KMS\. You cannot manage the Image Builder KMS key owned by Image Builder\. 

For more information about managing your KMS keys with AWS Key Management Service, see [Getting Started](https://docs.aws.amazon.com/kms/latest/developerguide/getting-started.html) in the AWS Key Management Service Developer Guide\.

## Internetwork Traffic Privacy in EC2 Image Builder<a name="image-builder-internetwork"></a>

Connections are secured between Image Builder and on\-premises locations, between AZs within an AWS Region, and between AWS Regions through HTTPS\. There are no direct connections between accounts\.