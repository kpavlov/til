# Terraform

## Importing 

check if you have the proper environment variables for AWS credentials?

   (env | grep AWS)
   
[Terraformer](https://github.com/GoogleCloudPlatform/terraformer) to import actual configuration


> I find since terraform 0.15.x, when you “terraform import” and then do a “terraform show”, 
> the format of the state file is valid HCL and can be copy/pasted into your .tf files.

https://github.com/hashicorp/terraform/pull/28874 - [`terraform add`](https://github.com/hashicorp/terraform/blob/main/website/docs/cli/commands/add.html.md) generates resource configuration templates which can be filled out and used to create resources.
