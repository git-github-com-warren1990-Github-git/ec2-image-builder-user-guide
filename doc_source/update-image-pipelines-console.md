# Update AMI image pipelines \(console\)<a name="update-image-pipelines-console"></a>

After you have created an Image Builder image pipeline for your AMI image, you can make changes to the infrastructure configuration and distribution settings from the Image Builder console\.

To update an image pipeline with a new image recipe, you must use the AWS CLI\. For more information, see [Update AMI image pipelines \(AWS CLI\)](cli-update-image-pipeline.md) in this guide\.

**Choose an existing Image Builder pipeline**

1. Open the EC2 Image Builder console at [https://console\.aws\.amazon\.com/imagebuilder/](https://console.aws.amazon.com/imagebuilder/)\.

1. To see a list of the image pipelines created under your account, choose **Image pipelines** from the navigation pane\.
**Note**  
The list of image pipelines includes an indicator for the type of output image that is created by the pipeline – AMI or Docker\.

1. To view details or edit a pipeline, choose the **Pipeline name** link\. This opens the detail view for the pipeline\.
**Note**  
You can also select the check box next to the **Pipeline name**, then choose **View detail**\.

## Pipeline details<a name="image-pipeline-details"></a>

The pipeline details page includes the following sections:

****Summary****  
The section at the top of the page summarizes key details for the pipeline that are visible with any of the detail tabs open\. The details displayed in this section are editable only on their respective detail tabs\.

**Detail tabs**
+ **Output images** – Shows output images that the pipeline has produced\.
+ **Image recipe** – Shows recipe details\. After you create a recipe, you cannot edit it\. You must create a new version of the recipe from the **Image recipes** page in the Image Builder console, or by using Image Builder commands in the AWS CLI\. For more information, see [Manage recipesRecipes](manage-recipes.md)\.
+ **Infrastructure configuration** – Shows editable information for configuring your build pipeline infrastructure\.
+ **Distribution settings** – Shows editable information for AMI distribution\.
+ **EventBridge rules** – For the selected **Event Bus**, shows EventBridge rules that target the current pipeline\. Includes **Create event bus** and **Create rule** actions that link to the EventBridge console\. For more information about this tab, see [Use EventBridge rules](ev-rules-for-pipeline.md)\.

## Edit infrastructure configuration for your pipeline<a name="pipelines-edit-infra-config"></a>

Infrastructure configuration includes the following details that you can edit after creating the pipeline:
+ The **Description** for your infrastruction configuration\.
+ The **IAM role** to associate with the instance profile\.
+ **AWS infrastructure**, including the **Instance type** and an **SNS topic** for notifications\.
+ **VPC, subnet, and security groups**\.
+ **Troubleshooting settings**, including **Terminate instance on failure**, the **Key pair** for connecting, and an optional S3 bucket location for instance logs\.

To edit infrastructure configuration from the pipeline details page, follow these steps:

1. Choose the **Infrastructure configuration** tab\.

1. Choose **Edit** from the upper right corner of the **Configuration details** panel\.

1. When you are ready to save updates you've made to your infrastructure configuration, choose **Save changes**\.

## Edit distribution settings for your pipeline<a name="pipelines-edit-dist-settings"></a>

Distribution settings include the following details that you can edit after creating the pipeline:
+ The **Description** for your distribution settings\.
+ **Region settings** for the Regions where you distribute your image\. Region 1 defaults to the Region where you created the pipeline\. You can add Regions for distribution with the **Add Region** button, and you can remove all Regions except Region 1\.

  **Region settings** include:
  + Target **Region**
  + The **Output AMI name**
  + **Launch permissions**, and accounts to share them with
  + Associated licenses \(**Associate license configurations**\)
**Note**  
License Manager settings will not replicate across AWS Regions that must be enabled in your account, for example, between the `ap-east-1` \(Hong Kong\) and the `me-south-1` \(Bahrain\) Regions\. 

To edit your distribution settings from the pipeline details page, follow these steps:

1. Choose the **Distribution settings** tab\.

1. Choose **Edit** from the upper right corner of the **Distribution details** panel\.

1. When you are ready to save your updates, choose **Save changes**\.

## Edit the build schedule for your pipeline<a name="pipelines-edit-build-schedule"></a>

The **Edit pipeline** page includes the following details that you can edit after creating the pipeline:
+ The **Description** for your pipeline\.
+ **Enhanced metadata collection**\. This is turned on by default\. To turn it off, clear the **Enable enhanced metadata collection** check box\.
+ The **Build schedule** for your pipeline\. You can change your **Schedule options** and all of the settings here\.

To edit your pipeline from the pipeline details page, follow these steps:

1. In the upper right corner of the pipeline details page, choose **Actions**, and then **Edit pipeline**\.

1. When you are ready to save your updates, choose **Save changes**\.

**Note**  
For more information about scheduling your build using cron expressions, see [Use cron expressions in EC2 Image Builder](cron-expressions.md)\.