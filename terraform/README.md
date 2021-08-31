# Terraform

## Importing 

check if you have the proper environment variables for AWS credentials?

   (env | grep AWS)
   
[Terraformer](https://github.com/GoogleCloudPlatform/terraformer) to import actual configuration


> I find since terraform 0.15.x, when you “terraform import” and then do a “terraform show”, 
> the format of the state file is valid HCL and can be copy/pasted into your .tf files.

https://github.com/hashicorp/terraform/pull/28874 - [`terraform add`](https://github.com/hashicorp/terraform/blob/main/website/docs/cli/commands/add.html.md) generates resource configuration templates which can be filled out and used to create resources.


## Setting version

versions.tf:
~~~hcl versions.tf
//https://www.terraform.io/docs/language/expressions/version-constraints.html  

terraform {
  required_version = "~> 1.0.5"

  required_providers {
    datadog = {
      source = "DataDog/datadog"
      version = "~> 3.3.0"
    }
  }
}
~~~

## Links

- [2020.01.29 Антон Бабенко - Terraform & Terragrunt](https://www.youtube.com/watch?v=PLJygZnFxQA)
