# Manage EC2 Image Builder infrastructure configuration<a name="manage-infra-config"></a>

Infrastructure configurations allow you to specify the infrastructure within which to build and test your EC2 Image Builder image\. Infrastructure settings include:
+ Instance types for your build and test infrastructure\. We recommend specifying more than one instance type because this allows Image Builder to launch an instance from a pool with sufficient capacity\. This can reduce your transient build failures\.
+ An instance profile that provides your build and test instances with the permissions that are required to perform customization activities\. For example, if you have a component that retrieves resources from Amazon S3, the instance profile requires permissions to access those files\. The instance profile also requires a minimal set of permissions for EC2 Image Builder to successfully communicate with the instance\. For more information, see [Prerequisites](image-builder-setting-up.md)\.
+ The VPC, subnet, and security groups for your pipeline's build and test instances\.
+ The Amazon S3 location where Image Builder stores application logs from your build and testing\. If you configure logging, the instance profile specified in your infrastructure configuration must have `s3:PutObject` permissions for the target bucket \(`arn:aws:s3:::BucketName/*`\)\.
+ An Amazon EC2 key pair that allows you to log on to your instance to troubleshoot if your build fails and you set `terminateInstanceOnFailure` to `false`\.
+ An SNS topic to which Image Builder sends event notifications\.
**Note**  
If your SNS topic is encrypted, the key that is used to encrypt the SNS topic must reside in the account that the Image Builder service runs under\. Image Builder is unable to send notifications to SNS topics that are encrypted using keys from other accounts\.

You can create and manage infrastructure configurations using the Image Builder console, through the Image Builder API, or with imagebuilder commands in the AWS CLI\.

This section covers how to list, view, and create infrastructure configurations\.

**Topics**
+ [List and view infrastructure configuration details](infra-config-details.md)
+ [Create and update infrastructure configurations](create-infra-config.md)

**Tip**  
When you have multiple resources of the same type, tagging helps you to identify a specific resource based on the tags you've assigned to it\. For more information about tagging your resources using Image Builder commands in the AWS CLI, see the [Tag resources](tag-resources.md) section of this guide\.